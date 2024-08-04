};
  const tableColumns = [
    {
      title: "N0.",
      dataIndex: "sl",
      key: "sl",
      width: "5%",
      render: (text, record, index) => index + 1,
    },
    {
      title: "Item Name",
      dataIndex: "item_name",
      key: "item_name",
      width: "15%",
    },
    ...(is_serial === "yes"
      ? [
        {
          title: "Serials",
          dataIndex: "serials",
          key: "serials",
          width: "14%",
          render: (serials) =>
            serials ? (
              <span>
                (
                {serials.map((serial) => (
                  <span key={serial.serial_number}>
                    {serial.serial_number},{" "}
                  </span>
                ))}
                )
              </span>
            ) : null,
        },
      ]
      : []),
    ...(is_warehouse === "yes"
      ? [
        {
          title: "Warehouse",
          dataIndex: "warehouse_name",
          key: "warehouse_name",
          width: "10%",
        },
      ]
      : []),
    {
      title: "Quantity",
      dataIndex: "qty_display",
      key: "qty_display",

      width: "10%",
    },
    {
      title: "Rate (Per)",
      dataIndex: "item_rate",
      key: "item_rate",

      width: "15%",
      render: (item_rate, record) => (
        <span>
          {format(parseFloat(item_rate).toFixed(2))} ({record.per_unit_symbol})
        </span>
      ),
    },
    ...(is_cal_type === "individual"
      ? [
        {
          title: "Discount %",
          dataIndex: "item_discount_per",
          key: "item_discount_per",

          width: "10%",
        },
        {
          title: "VAT %",
          dataIndex: "item_tax_per",
          key: "item_tax_per",

          width: "10%",
        },
      ]
      : []),
    {
      title: "Total",
      dataIndex: "item_total",
      key: "item_total",

      width: "10%",
      render: (item_total) => (
        <span>{format(parseFloat(item_total).toFixed(2))}</span>
      ),
    },
    {
      title: "Actions",
      key: "actions",

      width: "6%",
      render: (_, record, index) => (
        <>
          <EditOutlined
            style={{
              cursor: "pointer",
              color: "#2e482e",
              marginLeft: "2px",
            }}
            onClick={() => editItemCart(record, index)}
          />
          <span style={{ width: "2px" }}> </span>
          <MinusCircleOutlined
            style={{
              cursor: "pointer",
              color: "#582727",
              marginLeft: "2px",
            }}
            onClick={() => itemCartItemRemove(index, record)}
          />
        </>
      ),
    },
  ];
