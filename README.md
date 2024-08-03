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
