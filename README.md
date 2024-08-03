  const isAllowed = (key) => {
    // Define your condition here
    const allowedKeys = ["Dashboard", "sales", "pos"]; // Example allowed keys
    return allowedKeys.includes(key);
  };

// Filter and map menuData
const filteredMenuData = menuData
  .filter(item => isAllowed(item.key))
  .map(item => {
    if (item.children) {
      item.children = item.children.filter(child => isAllowed(child.key));
    }
    return item;
  });

console.log(filteredMenuData);
 <Menu
            style={{ width: 200, backgroundColor: "#1F263E", color: "#FFFFFF" }}
            defaultSelectedKeys={["Dashboard"]}
            mode="inline"
          >
            {menuData.map((menu) =>
              menu.children ? (
                <Menu.SubMenu
                  key={menu.key}
                  title={menu.label}
                  icon={menu.icon}
                >
                  {menu.children.map((child) => (
                    <Menu.Item key={child.key} icon={child.icon}>
                      <Link to={child.link}>{child.label}</Link>
                    </Menu.Item>
                  ))}
                </Menu.SubMenu>
              ) : (
                <Menu.Item key={menu.key} icon={menu.icon}>
                  <Link to={menu.link}>{menu.label}</Link>
                </Menu.Item>
              )
            )}
            <div style={{ display: 'flex', width: '100%', alignItems: 'center', justifyContent: 'center', paddingTop: '25%' }}>
              <img src={logoIcon} />
            </div>
          </Menu>

          const accessChecker = (accessName) => {
  let auth = JSON.parse(sessionStorage.getItem("auth_info"));
  if (auth.access != undefined || auth.access.length != 0) {
    let access = JSON.parse(auth.access);
    return access.indexOf(accessName);
  } else {
    return false;
  }
};
const filteredMenuData = menuData
  .map((item) => {
    if (item.children) {
      const filteredChildren = item.children.filter((child) => isAllowed(child.key));
      if (filteredChildren.length > 0) {
        return {
          ...item,
          children: filteredChildren,
        };
      }
      return null;
    } else if (isAllowed(item.key)) {
      return item;
    }
    return null;
  })
  .filter(Boolean);
