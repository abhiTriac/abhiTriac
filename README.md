router.post(`/api/save-role-access`, async (req, res, next) => {

  let transaction;
  try {
    console.log("try");
    transaction = await Tran.sequelize.transaction();
    console.log("access");
    let payLoad = req.body;
    let roles = payLoad.data
    console.log('roles', roles);
    for (const role of roles) {
      const countingQuery = `
        SELECT * FROM tbl_role_access
        WHERE institution_id = :institution_id
        AND role_id = :role_id
        AND access = :access
      `;

      const counting = await Tran.sequelize.query(countingQuery, {
        replacements: {
          institution_id: payLoad.institution_id,
          role_id: payLoad.role_id,
          access: role.value,
        },
        type: Tran.sequelize.QueryTypes.SELECT,
        transaction,
      });
      const newRecord = {
        institution_id: payLoad.institution_id,
        role_id: payLoad.role_id,
        access: role.value,
        access_type: role.access,
        tab: role.tab,
      };
      if (counting.length == 0) {
        await Tran.create("tbl_role_access", newRecord, transaction);
      } else {
        const updateQuery = `
        UPDATE tbl_role_access
        SET access_type = :access_type ,
         tab = :tab
        WHERE access = :access
        AND institution_id = :institution_id
        AND role_id = :role_id
      `;

        await Tran.sequelize.query(updateQuery, {
          replacements: newRecord,
          transaction,
        });
      }
    }
    await transaction.commit();
    res.json({ message: `Successfully Done.. ` });
  }
  catch (err) {

  }
})
