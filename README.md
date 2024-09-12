router.post("/api/save-role-access", async (req, res) => {
  const { role_id, institution_id, data } = req.body;
  if (!role_id || !institution_id || !Array.isArray(data)) {
    return res.status(400).json({ message: "Invalid request data" });
  }


  console.log('data', data, role_id, institution_id);

  try {
    // Iterate over the data array to insert or update each record
    for (item of data) {
      let obj = {
        role_id: role_id,
        institution_id: institution_id,
        access: item.value,
        access_type: item.access,
        tab: item.tab
      }
      let [existErr, exist] = await _p(
        db.countRows(
          `select * from tbl_role_access
          where role_id =? and institution_id=? and access =? `,
          [role_id, institution_id, obj.access]
        )
      ).then((res) => {
        console.log('res', res);
        return res
      });

      if (exist > 0) {
        console.log("exit works");
        // delete obj.access;
        // delete obj.institution_id;
        // delete obj.tab;
        // delete obj.role_id;
        let [updateErr, update] = await _p(
          db.query(
            `update tbl_role_access 
            set access_type =?
            where role_id =? and institution_id=?`,
            [obj.access_type,obj.role_id,obj.institution_id]
           )
        ).then((res) => {
          return res;
        });
        console.log('save', update);
      }
      let [saveErr, save] = await _p(
        db.insert("tbl_role_access", obj)
      ).then((res) => {
        return res;
      });
      console.log('save', save);

      if (saveErr && !save) {
        next(saveErr);
      } else {
        res.json({
          error: false,
          msg: `Role created successfully.`,
        });
      }
    }

  } catch (error) {
    console.error("Error saving role access:", error);
    return res.status(500).json({ message: "Internal Server Error" });
  }
});
