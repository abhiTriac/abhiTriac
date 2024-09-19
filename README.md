Error: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?, ?)' at line 1
    at PromisePool.query (C:\Users\abhijith\Projects\fortherp\api\node_modules\mysql2\promise.js:356:22)
    at Transaction.create (C:\Users\abhijith\Projects\fortherp\api\src\utils\TranDB.js:41:28)
    at C:\Users\abhijith\Projects\fortherp\api\src\controlers\administration.js:4709:36
    at processTicksAndRejections (node:internal/process/task_queues:96:5)


  let [save, _] = await Tran.create(`tbl_items`, payLoad, connection);

  async create(tableName, data, transaction) {
    const columns = Object.keys(data).join(', ');
    const placeholders = Object.keys(data).map(() => '?').join(', ');

    let query = `INSERT INTO ${tableName} (${columns}) VALUES (${placeholders})`;

    const values = Object.values(data).map(value => (value === undefined || value === null ? '' : value));


    return await this.pool.query(query, {
      replacements: values,
      type: QueryTypes.INSERT,
      transaction: transaction,
    });
  }
