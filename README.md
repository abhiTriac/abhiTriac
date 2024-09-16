   <Menu
            style={{ width: 200, backgroundColor: "#1F263E", color: "#FFFFFF" }}
            defaultSelectedKeys={["Dashboard"]}
            mode="inline"
          >
            {filteredMenuData
              .filter(child => accessChecker(child.key) == true)
              .map((menu) =>
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
            <div style={{ display: 'flex', width: '100%', alignItems: 'center', justifyContent: 'center', paddingTop: '43%' }}>
              <img src={logoIcon} style={{ width: '118px' }} />
            </div>
          </Menu>
