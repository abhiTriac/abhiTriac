router.post("/api/upload", upload.single("file"), async (req, res, next) => {
  if (!req.file) {
    return res.status(400).json({ message: "No file provided. Please upload a valid CSV file." });
  }

  const filePath = req.file.path;
  let skippedRows = [];
  const transactions = [];

  try {
    const { user_id, branch_id, selected_account } = req.body;

    if (!user_id || !branch_id || !selected_account) {
      return res.status(400).json({
        message: "Required fields missing in the request body.",
        requiredFields: ["user_id", "branch_id", "selected_account"],
      });
    }

    const fileChecksum = await generateFileChecksum(filePath);

    // Check for duplicate file entry before starting a transaction
    const duplicateFileCount = await Tran.countRows(
      `SELECT COUNT(*) AS count FROM uploaded_files WHERE checksum = ? AND branch_id = ?`,
      [fileChecksum, branch_id]
    );

    if (duplicateFileCount > 0) {
      console.warn("Duplicate file detected. Skipping further processing.");
      fs.unlink(filePath, (err) => err && console.error("File deletion error:", err));
      return res.status(201).json({ message: "File has already been uploaded and processed." });
    }

    // Start transaction after confirming no duplicates
    const dbTransaction = await Tran.sequelize.transaction();

    try {
      fs.createReadStream(filePath)
        .pipe(csv())
        .on("data", (row) => {
          const { Date: date, pay_to, into_acc_id, Description, Credit, Debit } = row;
          const parsedDate = parseDate(date);

          if (!parsedDate || isNaN(new Date(parsedDate).getTime())) {
            skippedRows.push({ row, reason: "Invalid date" });
            return;
          }

          transactions.push({
            Date: parsedDate,
            into_acc_id,
            pay_to,
            narration: Description,
            Credit: parseFloat(Credit) || 0,
            Debit: parseFloat(Debit) || 0,
          });
        })
        .on("error", async (err) => {
          console.error("Error reading CSV:", err);
          await dbTransaction.rollback();
          next(err);
        })
        .on("end", async () => {
          try {
            const { branch_id, status = "a", selected_account } = req.body;

            const processTransaction = async ({ Date, narration, Credit, Debit }) => {
              if (Debit > 0) {
                const inc_code = await incCode(req);
                const incData = {
                  into_acc_id: selected_account,
                  inc_code,
                  inc_total: Debit,
                  narration,
                  branch_id,
                  is_csv: 1,
                  created_Date: Date,
                  created_By: req.user.user_id,
                  status,
                };
                let [save] = await Tran.create("incomes", incData, dbTransaction);
                await Tran.create("income_details", { inc_amount: Debit, status, branch_id, inc_id: save }, dbTransaction);
              }

              if (Credit > 0) {
                const exp_code = await expCode(req);
                const expData = {
                  from_acc_id: selected_account,
                  exp_code,
                  exp_total: Credit,
                  narration,
                  branch_id,
                  is_csv: 1,
                  created_Date: Date,
                  created_By: req.user.user_id,
                  status,
                };
                let [save] = await Tran.create("expenses", expData, dbTransaction);
                await Tran.create("expense_details", { exp_amount: Credit, status, branch_id, exp_id: save }, dbTransaction);
              }
            };

            await Promise.all(transactions.map(processTransaction));

            // Insert into uploaded_files table only after successful transaction commit
            await Tran.create("uploaded_files", { userid: user_id, checksum: fileChecksum, branch_id }, dbTransaction);

            await dbTransaction.commit();
            console.log("All transactions processed and committed successfully.");

            fs.unlink(filePath, (err) => err && console.error("File deletion error:", err));

            res.json({ message: "File processed and data inserted", skippedRows });
          } catch (error) {
            await dbTransaction.rollback();
            console.error("Transaction failed:", error);
            next(error);
          }
        });
    } catch (error) {
      await dbTransaction.rollback();
      console.error("Error processing transactions:", error);
      next(error);
    }
  } catch (error) {
    console.error("Unexpected error:", error);
    next(error);
  }
});
