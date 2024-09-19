async create(tableName, data, transaction) {
    // Check if data is empty
    if (Object.keys(data).length === 0) {
        throw new Error("No data provided for insert.");
    }

    const columns = Object.keys(data).join(', ');
    const placeholders = Object.keys(data).map(() => '?').join(', ');

    let query = `INSERT INTO ${tableName} (${columns}) VALUES (${placeholders})`;

    // Filter out undefined or null values before mapping
    const values = Object.values(data).map(value => (value === undefined ? null : value));

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
