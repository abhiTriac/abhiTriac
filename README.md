 if (signupRecord) {
          let tableRoleObj = {
            user_id: signupRecord[0].user_id,
            role_id: reqData.selectedUserRole.value
          };
          console.log("tableRoleObj", tableRoleObj);
          console.log("tableRoleObj1", signupRecord[0].user_id);
          let [roleInsertDataErr, roleInsertData] = await _p(db.insert(roleTableName, tableRoleObj)).then(result => {
            return result
          })
        }
