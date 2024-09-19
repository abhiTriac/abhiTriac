Error: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ', `type` = 'SELECT', `transaction` = '[object Object]'  and status= 'a'' at line 1
    at PromisePool.query (C:\Users\abhijith\Projects\fortherp\api\node_modules\mysql2\promise.js:356:22)
    at Transaction.countRows (C:\Users\abhijith\Projects\fortherp\api\src\utils\TranDB.js:98:36)
    at C:\Users\abhijith\Projects\fortherp\api\src\controlers\administration.js:4693:32
    at runMicrotasks (<anonymous>)
    at processTicksAndRejections (node:internal/process/task_queues:96:5)
 async countRows(query, replacements, transaction) {
    const result = await this.pool.query(query, {
      replacements: replacements,
      type: QueryTypes.SELECT,
      transaction: transaction,
    });

    return result.length; // Return both rows and count
  } 
if (payLoad.action == "create") {
        let exist = await Tran.countRows(
          `select item_name from tbl_items where item_name=?  and status= 'a' `,
          [payLoad.item_name],
          connection
        );
        console.debug("exist: ", exist);

        if (exist > 0) {
          res.json({
            error: true,
            msg: `Item Name Already Exist.`,
          });
          return false;
        }
        delete payLoad.action;
        delete payLoad.item_id;
        delete payLoad.prev_photo;
        let [save, _] = await Tran.create(`tbl_items`, payLoad, connection);

        await stockUpdate(
          "opening_qty",
          "plus",
          save,
          payLoad.opening_qty,
          req.user.user_branch_id,
          0,
          connection
        );

        await itemCostUpdate(
          "plus",
          save,
          payLoad.opening_qty,
          payLoad.opening_rate,
          0,
          req.user.user_branch_id,
          0,
          connection
        );

        if (_ && !save) {
          next(saveErr);
        } else {
          // end

          res.json({
            error: false,
            msg: `Item Name create successful.`,
          });
        }
      }
      
