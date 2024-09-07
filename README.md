 const map = new Map();
  
  array.forEach(item => {
    const key = JSON.stringify(item); // Convert object to string
    if (!map.has(key)) {
      map.set(key, item);
    }
  });

  return Array.from(map.values());
