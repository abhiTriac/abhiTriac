  <Menu
            style={{ width: 200, backgroundColor: "#1F263E", color: "#FFFFFF" }}
            defaultSelectedKeys={["Dashboard"]}
            mode="inline"
          >
            {filteredMenuData.map((menu, menuIndex) =>
              menu.children ? (
                <Menu.SubMenu
                  key={generateUniqueKey(menu.key, menuIndex)}
                  title={menu.label}
                  icon={menu.icon}
                >
                  {menu.children.map((child, childIndex) => (
                    <Menu.Item key={generateUniqueKey(`${menu.key}-${child.key}`, childIndex)} icon={getChildIcon(child.key)}>
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
            <div style={{ display: 'flex', width: '100%', alignItems: 'center', justifyContent: 'center', paddingTop: '43%' }}>
              <img src={logoIcon} alt="logo" style={{ width: '118px' }} />
            </div>
          </Menu>
