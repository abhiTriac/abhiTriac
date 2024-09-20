   const query = "SELECT * FROM tbl_role_access WHERE role_id IN (" + rolesString + ")";
          console.log('query: ', query);

          let [accessListErr, accessList] = await _p(
            db
              .query(query,
                [rolesString]
              )
              .then((res) => {
                return res;
              })
          );
