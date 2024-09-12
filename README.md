router.post("/api/save-role-access", async (req, res) => {
  const { role_id, institution_id, data } = req.body;

  // Validate the request body
  if (!role_id  !institution_id  !Array.isArray(data)) {
    return res.status(400).json({ message: "Invalid request data" });
  }

  console.log("data", data, role_id, institution_id);

  try {
    // Iterate over the data array to insert or update each record
    for (let item of data) {
      let obj = {
        role_id: role_id,
        institution_id: institution_id,
        access: item.value,
        access_type: item.access,
        tab: item.tab,
      };

      // Check if the role access entry already exists
      const [existErr, exist] = await _p(
        db.countRows(
          SELECT * FROM tbl_role_access WHERE role_id = ? AND institution_id = ? AND access = ?,
          [role_id, institution_id, obj.access]
        )
      );

      if (existErr) {
        console.error("Error checking existence:", existErr);
        return res.status(500).json({ message: "Internal Server Error" });
      }

      if (exist > 0) {
        // Update existing access if the record exists
        const [updateErr, update] = await _p(
          db.query(
            UPDATE tbl_role_access SET access_type = ? WHERE role_id = ? AND institution_id = ? AND access = ?,
            [obj.access_type, obj.role_id, obj.institution_id, obj.access]
          )
        );

        if (updateErr) {
          console.error("Error updating role access:", updateErr);
          return res.status(500).json({ message: "Internal Server Error" });
        }

        console.log("Updated role access:", update);
      } else {
        // Insert new role access if it does not exist
        const [saveErr, save] = await _p(db.insert("tbl_role_access", obj));

        if (saveErr) {
          console.error("Error saving role access:", saveErr);
          return res.status(500).json({ message: "Internal Server Error" });
        }

        console.log("Saved new role access:", save);
      }
    }

    // Send a success response after processing all data
    return res.json({
      error: false,
      msg: "Role access created/updated successfully.",
    });
  } catch (error) {
    console.error("Error saving role access:", error);
    return res.status(500).json({ message: "Internal Server Error" });
  }
});
