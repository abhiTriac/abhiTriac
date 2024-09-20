 let [rolesErr, roles] = await _p(
            db
              .query(
                `SELECT * FROM tbl_user_role WHERE user_id=? `,
                [user_id]
              )
              .then((res) => {
                return res;
              })
          );
          console.log('roles: ', roles);
          const rolesExtracted = roles.map(userRole => userRole.role_id);
          const rolesString = rolesExtracted.join(',');
          console.log('rolesString: ', rolesString);

          const query = `SELECT * FROM tbl_role_access WHERE role_id IN (${rolesString})`;
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
