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
  {
    key: "Dashboard",
    label: "Dashboard",
    icon: <img src={dashboardIcon} alt="dashboard" className="menu-icon" />,
    link: "/dashboard",
  },
  {
    key: "sales",
    label: "Sales",
    icon: <img src={salesIcon} className="menu-icon" alt="Sales" />,
    children: [
      {
        key: "sales_entry",
        label: "Sales Entry",
        link: "/sales/sales-entry",
      },
      {
        key: "customer_entry",
        label: "Customer Entry",
        link: "/sales/customer-entry",
      },
      // More children...
    ],
  },
  {
    key: "pos",
    label: "POS",
    icon: <img src={posIcon} alt="POS" className="svgIcon" style={{ color: 'white', }} />,
    link: "/pos/pos-entry",
  },
  {
    key: "quotation",
    label: "Quotation",
    icon: <img src={quotationIcon} alt="quotationIcon" className="menu-icon" />,
    children: [
      {
        key: "quotation_entry",
        label: "Quotation Entry",
        link: "/quotation/quotation-entry",
      },
      // More children...
    ],
  },
  // More menu items...
];

const tabsKeys = tabs.map(tab => tab.tab);

const filteredMenuData = menuData
  .filter(item => tabsKeys.includes(item.key))
  .map(item => {
    if (item.children) {
      const filteredChildren = item.children.filter(child => tabsKeys.includes(child.key));
      return {
        ...item,
        children: filteredChildren
      };
    }
    return item;
  })
  .filter(item => item.key || (item.children && item.children.length > 0));

// Now `filteredMenuData` contains only those menu items and their children that match the tabs.

console.log(filteredMenuData);
