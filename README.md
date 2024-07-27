const columns = [
    {
      name: "User ID",
      options: {
        filter: false,
        sort: false,
        customBodyRender: (value, tableMeta) => {
          return <>{parseFloat(tableMeta.rowIndex) + 1}</>;
        },
      },
      headerStyle: {
        textAlign: "left",
      },
    },
    {
      name: "Staff_user",
      label: "Staff User",
      options: {
        filter: true, sort: true,

      },
    },
    { name: "user_role", label: "User Role", options: { filter: true, sort: true } },

    {
      name: "status",
      label: "Status",
      options: {
        filter: true, sort: true,
        customBodyRender: (value) => (
          <div style={{ backgroundColor: 'red', width: 'fit-content',  }}>{value}</div>
        )
      },
    },
    {
      name: "leave_applied_to",
      label: "Leave Applied On ",
      options: { filter: true, sort: true, },
    },
    {
      name: "Shift_time",
      label: "Shift Time  ",
      options: { filter: true, sort: true, },
    },

    {
      name: "From_date",
      label: "From Date ",
      options: { filter: true, sort: true, },
    }, {
      name: "To_date",
      label: "To Date ",
      options: { filter: true, sort: true, },
    },
  ];
