const express = require('express');
const router = express.Router();
const db = require('./database'); // Adjust the path as necessary

router.post('/api/save-role-access', async (req, res) => {
  try {
    const { data: roles, institution_id, role_id } = req.body;

    if (!Array.isArray(roles) || roles.length === 0) {
      return res.status(400).json({ message: 'Invalid input array' });
    }

    for (const role of roles) {
      // Check if record exists
      const [rows] = await db.query(
        `SELECT id FROM tbl_role_access
         WHERE institution_id = ? AND role_id = ? AND access = ?`,
        {
          replacements: [institution_id, role_id, role.value],
          type: db.QueryTypes.SELECT
        }
      );

      if (rows.length > 0) {
        // Update existing record
        await db.query(
          `UPDATE tbl_role_access
           SET access_type = ?, tab = ?
           WHERE role_id = ? AND access = ? AND institution_id = ?`,
          {
            replacements: [role.access, role.tab, role_id, role.value, institution_id]
          }
        );
      } else {
        // Insert new record
        await db.query(
          `INSERT INTO tbl_role_access (role_id, access, access_type, institution_id, tab)
           VALUES (?, ?, ?, ?, ?)`,
          {
            replacements: [role_id, role.value, role.access, institution_id, role.tab]
          }
        );
      }
    }

    res.json({ message: 'Successfully Done!' });

  } catch (err) {
    console.error('Error:', err);
    res.status(500).json({ error: 'An error occurred while processing the request.' });
  }
});

module.exports = router;
