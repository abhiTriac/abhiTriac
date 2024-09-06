 router.post(`/api/save-role-access`, async (req, res, next) => {
//   try {
//     const payLoad = req.body;
//     const roles = payLoad.data;
//     console.log('payload', payLoad);
//     // Check if the array is valid
//     // if (!Array.isArray(roles) || roles.length === 0) {
//     //   return res.status(400).json({ message: 'Invalid input array' });
//     // }
//     for (const role of roles) {
//       let [existErr, exist] = await _p(
//         db.countRows(
//           `select id from tbl_role_access
//           where institution_id =? and role_id=?  and access =?`,
//           [payLoad.institution_id, payLoad.role_id, role.value]
//         )
//       ).then((res) => {
//         return res
//       });
//       console.log('exisr', exist);
//       if (exist > 0) {
//         console.log('exisr if', exist);
//         let [saveErr, save] = await _p(
//           db.update(`tbl_role_access`,
//             {

//               access_type: role.access,
//               institution_id: payLoad.institution_id,
//               tab: role.tab
//             }, { role_id: 5, access: role.value })).then((res) => {
//               console.log('res', res);
//             })

//       }
//       else {
//         await Tran.create(
//           `tbl_role_access`,
//           {
//             role_id: payLoad.role_id,
//             access: role.value,
//             access_type: role.access,
//             institution_id: payLoad.institution_id,
//             tab: role.tab
//           })
//       }
//     }
