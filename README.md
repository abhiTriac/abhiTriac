async create(tableName, data, transaction) {
    // Filter out undefined, null, or empty string values if necessary
    const validData = Object.fromEntries(
        Object.entries(data).filter(([_, value]) => value !== undefined && value !== null)
    );

    // Ensure there are no empty values if your schema does not allow them
    const columns = Object.keys(validData).join(', ');
    const placeholders = Object.keys(validData).map(() => '?').join(', ');

    let query = `INSERT INTO ${tableName} (${columns}) VALUES (${placeholders})`;

    const values = Object.values(validData);

    console.debug("Executing query: ", query);
    console.debug("With values: ", values);

    // Execute the query
    const [result] = await this.pool.query(query, {
        replacements: values,
        type: QueryTypes.INSERT,
        transaction: transaction,
    });

    return result; // Return the result of the insert operation
}
