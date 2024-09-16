const filteredMenuData = menuData
  .filter(menuItem => tabs.some(tab => tab.tab === menuItem.key)) // Filter top-level menu items
  .map(menuItem => {
    if (menuItem.children) {
      // Filter children based on accessChecker
      const filteredChildren = menuItem.children.filter(child => accessChecker(child.key));
      return {
        ...menuItem,
        children: filteredChildren,
      };
    }
    return menuItem;
  })
  .filter(item => item.children.length > 0 || !item.children); // Remove items with no children if they have children
