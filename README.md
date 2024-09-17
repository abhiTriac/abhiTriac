router.post('/api/signup', signupValidator, rejet_invalid, async (req, res, next) => {
  let tableName = `tbl_users`

  let [checkDuplicateUsernameErr, checkDuplicateUsername] =
    await _p(db.query(`select user_name from ${tableName} where user_name=?`, req.body.user_name)).then(result => {
      return result;
    })
  if (checkDuplicateUsernameErr && !checkDuplicateUsername) {
    return next(checkDuplicateUsernameErr)
  } else {
    if (checkDuplicateUsername.length > 0) {
      res.status(200).json({
        error: true,
        message: "username already exists."
      });
    } else {
      // Signup next script
      let reqData = req.body;
      let shunks = generate(req.body.user_password);
      let user_password = `${shunks.salt}.${shunks.hash}`;
      let saveObj = {
        user_full_name: reqData.user_full_name,
        user_email: reqData.user_email,
        user_branch_id: reqData.selectedBranch.branch_id,
        user_warehouse_id: reqData.selectedWarehouse != null ? reqData.selectedWarehouse.warehouse_id : 0,
        user_role: reqData.selectedUserRole.user_role,
        user_label: reqData.selectedUserRole.user_label,
        user_full_name: reqData.user_full_name,
        user_name: reqData.user_name,
        user_password: user_password,
        user_access: '[]',
        user_status: 'active',
        user_created_iso_dt: getCurrentISODT(),
        user_updated_iso_dt: getCurrentISODT(),
        user_created_by: req.user.user_id,
        customer_id: reqData.customer_id,
        employee_id:reqData.employee_id,
        acc_type: reqData.acc_type,
      }
      let [signupErr, signupData] = await _p(db.insert(tableName, saveObj)).then(result => {
        return result;
      })
      if (signupErr && !signupData) {
        return next(signupErr)
      } else {
        let [signupRecordErr, signupRecord] = await _p(db.query(`select * from ${tableName} where user_id=?`, signupData.insertId)).then(result => {
          return result
        })
        if (signupRecordErr && !signupRecord) {
          return next(signupRocordErr)
        }

        res.status(200).json({
          error: false,
          message: 'User account created successfully'
        })
      }
    }
  }
})
