async countRows(query, replacements, connection) {
    const result = await connection.query(query, {
      replacements: replacements,
      type: QueryTypes.SELECT,
    });

    return result.length; // Return both rows and count
  }
