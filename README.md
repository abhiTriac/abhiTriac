  const handleChangeSelectItem = (value, option) => {
    if (item_name && items.length) {
    }
    selectedItemSet(option.props.obj);
    selectedUnitSet(null);
    if (option.props.obj != null) {
      item_discount_per_set(option.props.obj.discount_per);
      item_tax_per_set(option.props.obj.tax_per);
      conversion_set(option.props.obj.conversion);
      per_conversion_set(option.props.obj.units[0].conversion);
      item_rate_set(
        option.props.obj.item_rate === 0 ? "" : option.props.obj.item_rate
      );
    } else {
      item_rate_set("");
    }
    item_qty_set(0);
    retail_qty_set(0);
  };
