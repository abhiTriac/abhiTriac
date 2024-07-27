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
      filter: true, 
      sort: true,
    },
  },
  { 
    name: "user_role", 
    label: "User Role", 
    options: { 
      filter: true, 
      sort: true 
    } 
  },
  {
    name: "status",
    label: "Status",
    options: {
      filter: true, 
      sort: true,
      customBodyRender: (value) => {
        let backgroundColor = 'transparent';
        let color = 'black';

        if (value === 'Active') {
          backgroundColor = 'green';
          color = 'white';
        } else if (value === 'Inactive') {
          backgroundColor = 'red';
          color = 'white';
        } else if (value === 'Pending') {
          backgroundColor = 'yellow';
          color = 'black';
        }

        return (
          <div style={{ backgroundColor, color, padding: '4px 8px', borderRadius: '4px' }}>
            {value}
          </div>
        );
      }
    },
  },
  {
    name: "leave_applied_to",
    label: "Leave Applied On",
    options: { 
      filter: true, 
      sort: true, 
    },
  },
];
