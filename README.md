const getAccessType = (accessKey) => {
  const accessItem = accessList.find(item => item.access === accessKey);
  return accessItem ? accessItem.type : null; // Return type or null if not found
};
