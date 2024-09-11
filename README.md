Error: You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ', `type` = 'SELECT', `transaction` = '[object Or ', `type` = 'SELECT', `transaction` = '[object Object]'  and status= 'a'' at line 1
    at PromisePool.query (C:\Users\abhijith\Projects\fortherp\api\node_modules\mysql2\promise.js:356:22)
    at Transaction.countRows (C:\Users\abhijith\Projects\fortherp\api\src\utils\TranDB.js:98:36)
    at C:\Users\abhijith\Projects\fortherp\api\src\controlers\administration.js:4693:32
    at processTicksAndRejections (node:internal/process/task_queues:96:5)
router.post(`/api/save-account`, async (req, res, next) => {
  try {
    let payLoad = req.body;
    payLoad.create_by = req.user.user_id;
    payLoad.branch_id = req.user.user_branch_id;

    payLoad.acc_type_id = payLoad.acc_type.acc_type_id;
    payLoad.acc_type_name = payLoad.acc_type.acc_type_name;
    payLoad.acc_type_label = payLoad.acc_type.label;
    delete payLoad.acc_type;

    if (payLoad.action == "create") {
      let [existErr, exist] = await _p(
        db.countRows(
          `select acc_name from tbl_accounts where acc_name=? and branch_id = ? and status ='a'  `,
          [payLoad.acc_name, req.user.user_branch_id]
        )
      ).then((res) => {
        return res;
      });

      if (exist > 0) {
        res.json({
          error: true,
          msg: `Account Name Already Exists.`,
        });
        return false;
      }

      delete payLoad.action;
      delete payLoad.acc_id;

      let [saveErr, save] = await _p(db.insert("tbl_accounts", payLoad)).then(
        (res) => {
          return res;
        }
      );
      if (saveErr && !save) {
        next(saveErr);
      } else {
        //Record the new account creation in the activity table
        const insertObj = {
          activity_name: `Account created`,
          type: `c`,
          activity_created_by: req?.user?.user_id,
          created_at: getCurrentISODT(),
          user_branch_id: req?.user?.user_branch_id
        }
        const result = await db.insert(`tbl_activity`, insertObj)
        res.json({
          error: false,
          msg: `Account Created  Successfully.`,
        });
      }
    } else {
      let [existErr, exist] = await _p(
        db.countRows(
          `select acc_name from tbl_accounts where acc_name=? and branch_id = ? and acc_id !=?  and status ='a'   `,
          [payLoad.acc_name, req.user.user_branch_id, payLoad.acc_id]
        )
      ).then((res) => {
        return res;
      });

      if (exist > 0) {
        res.json({
          error: true,
          msg: `Account Name Already Exists.`,
        });
        return false;
      }

      let acc_id = payLoad.acc_id;
      delete payLoad.action;
      delete payLoad.acc_id;
      let [saveErr, save] = await _p(
        db.update("tbl_accounts", payLoad, { acc_id })
      ).then((res) => {
        return res;
      });
      if (saveErr && !save) {
        next(saveErr);
      } else {
        //Record the account update in the activity table
        const insertObj = {
          activity_name: `Account updated`,
          type: `u`,
          activity_created_by: req?.user?.user_id,
          created_at: getCurrentISODT(),
          user_branch_id: req?.user?.user_branch_id
        }
        const result = await db.insert(`tbl_activity`, insertObj)
        res.json({
          error: false,
          msg: `Account Name  updated successfully.`,
        });
      }
    }
  } catch (err) {
    next(err);
  }
});
