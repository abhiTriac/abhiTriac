TypeError: Cannot read properties of null (reading 'access')
    at accessList (functions.js:25:1)
    at isAllowed (Header.js:935:1)

const accessList = () => {
  let auth = JSON.parse(sessionStorage.getItem("auth_info"));
  if (auth.access != undefined || auth.access.length != 0) {
    let access = JSON.parse(auth.access);
    return access;
  }
  // else {
  //   return null
  // }
}
