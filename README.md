 const minExpiryValue = Math.min(...nonNullValues.map(value => value.days));
    nearestExpiry = nonNullValues.find(value => value.days === minExpiryValue);
