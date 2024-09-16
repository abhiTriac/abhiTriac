import React from 'react';
import { Menu } from 'antd';
import { Link } from 'react-router-dom';

// Sample icons - replace with actual imports
import dashboardIcon from 'path/to/dashboardIcon.png';
import salesIcon from 'path/to/salesIcon.png';
import posIcon from 'path/to/posIcon.png';
import quotationIcon from 'path/to/quotationIcon.png';
import orderIcon from 'path/to/orderIcon.png';
import serviceIcon from 'path/to/serviceIcon.png';
import purchaseIcon from 'path/to/purchaseIcon.png';
import manufactureIcon from 'path/to/manufactureIcon.png';
import inventoryIcon from 'path/to/inventoryIcon.png';
import accountsIcon from 'path/to/accountsIcon.png';
import hrIcon from 'path/to/hrIcon.png';
import reportIcon from 'path/to/reportIcon.png';
import crmIcon from 'path/to/crmIcon.png';
import settingIcon from 'path/to/settingIcon.png';
import logoIcon from 'path/to/logoIcon.png';

// Sample accessChecker function
const accessChecker = (key) => true; // Replace with actual logic

const tabs = [
  { tab: "sales" },
  { tab: "pos" },
  { tab: "reports" },
  { tab: "order" },
  { tab: "service" },
  { tab: "purchase" },
  { tab: "hrpayroll" },
  { tab: "accounts" },
  { tab: "inventory" },
  { tab: "manufacturing" }
];

const menuData = [
  // ... (same as your provided menuData)
];

const filteredMenuData = menuData
  .filter(item => tabs.some(tab => tab.tab === item.key))
  .map(item => {
    if (item.children) {
      const filteredChildren = item.children.filter(child => tabs.some(tab => tab.tab === child.key));
      return {
        ...item,
        children: filteredChildren,
      };
    }
    return item;
  })
  .filter(Boolean);

const getChildIcon = (key) => {
  switch (key) {
    case "sales_entry":
      return salesIcon;
    case "pos_entry":
      return posIcon;
    // Add other cases as needed
    default:
      return null; // Fallback icon
  }
};

const MyMenu = () => (
  <Menu
    style={{ width: 200, backgroundColor: "#1F263E", color: "#FFFFFF" }}
    defaultSelectedKeys={["Dashboard"]}
    mode="inline"
  >
    {filteredMenuData
      .filter(item => accessChecker(item.key))
      .map(menu =>
        menu.children ? (
          <Menu.SubMenu
            key={menu.key}
            title={menu.label}
            icon={menu.icon}
          >
            {menu.children.map(child => (
              <Menu.Item key={child.key} icon={getChildIcon(child.key)}>
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
);

export default MyMenu;
