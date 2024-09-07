router.post("/saveOrUpdateRoleAccess", async (req, res) => {
  const body = {
    role_id: 1,
    institution: 1,
    data: [
      { value: "sales", access: "read", tab: "sale" },
      { value: "sales_entry", access: "write", tab: "sale" },
      { value: "pos", access: "write", tab: "pos" },
      { value: "purchae", access: "write", tab: "order" },
    ],
  };
  const { role_id, institution, data } = body;

  if (!role_id || !institution || !Array.isArray(data)) {
    return res.status(400).json({ message: "Invalid request data" });
  }

  const sql = `INSERT INTO row_access (role_id, institution_id, access, access_type, tab) 
               VALUES (?, ?, ?, ?, ?)
               ON DUPLICATE KEY UPDATE 
               access_type = VALUES(access_type), tab = VALUES(tab)`;

  try {
    // Iterate over the data array to insert or update each record
    for (let i = 0; i < data.length; i++) {
      const { value, access, tab } = data[i];

      // Execute the SQL query with prepared statement to insert or update
      await db.query(sql, [role_id, institution, value, access, tab]);
    }

    return res
      .status(200)
      .json({ message: "Role access saved or updated successfully!" });
  } catch (error) {
    console.error("Error saving or updating role access:", error);
    return res.status(500).json({ message: "Internal Server Error" });
  }
});
