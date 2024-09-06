app.post('/save-or-update-output', (req, res) => {
    const outputArray = req.body;

    // Check if the array is valid
    if (!Array.isArray(outputArray) || outputArray.length === 0) {
        return res.status(400).json({ message: 'Invalid input array' });
    }

    // SQL query for insert or update
    const sqlQuery = `
        INSERT INTO role_access (tab, access) 
        VALUES ? 
        ON DUPLICATE KEY UPDATE 
        access = VALUES(access)
    `;

    const values = outputArray.map(item => [item.tab, item.access]);

    db.query(sqlQuery, [values], (error, results) => {
        if (error) {
            console.error('Error inserting/updating data:', error);
            return res.status(500).json({ message: 'Error saving or updating data' });
        }

        return res.status(200).json({ message: 'Data saved/updated successfully', data: results });
    });
});
