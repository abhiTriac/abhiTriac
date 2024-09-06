router.post('/api/save-role-access', async (req, res) => {
  let transaction;
  try {
    console.log("Starting transaction...");
    transaction = await sequelize.transaction(); // Ensure using sequelize's transaction

    const { data, institution_id, role_id } = req.body;

    console.log('Received roles:', data);

    for (const role of data) {
      // Check if record exists
      const countingQuery = `
        SELECT * FROM tbl_role_access
        WHERE institution_id = :institution_id
        AND role_id = :role_id
        AND access = :access
      `;

      const counting = await sequelize.query(countingQuery, {
        replacements: {
          institution_id,
          role_id,
          access: role.value,
        },
        type: sequelize.QueryTypes.SELECT,
        transaction,
      });

      const newRecord = {
        institution_id,
        role_id,
        access: role.value,
        access_type: role.access,
        tab: role.tab,
      };

      if (counting.length === 0) {
        // Insert new record
        await sequelize.query(
          `INSERT INTO tbl_role_access (institution_id, role_id, access, access_type, tab)
           VALUES (:institution_id, :role_id, :access, :access_type, :tab)`,
          {
            replacements: newRecord,
            transaction,
          }
        );
      } else {
        // Update existing record
        await sequelize.query(
          `UPDATE tbl_role_access
           SET access_type = :access_type,
               tab = :tab
           WHERE access = :access
           AND institution_id = :institution_id
           AND role_id = :role_id`,
          {
            replacements: newRecord,
            transaction,
          }
        );
      }
    }

    await transaction.commit();
    res.json({ message: 'Successfully Done!' });
  } catch (err) {
    if (transaction) await transaction.rollback(); // Rollback on error
    console.error('Error:', err);
    res.status(500).json({ error: 'An error occurred while processing the request.' });
  }
});
