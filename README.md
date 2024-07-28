  const columns = [
    {
      name: "user_id",
      label: "User ID",
      options: {
        filter: false,
        sort: true,
        customBodyRender: (value, tableMeta) => {
          return (<div style={{
            color: "#0265DC", fontWeight: '700', fontSize: '12px'
          }}>{value}</div>);
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
        setCellProps: () => ({
          style: {
            whiteSpace: 'nowrap',
            overflow: 'hidden',
            textOverflow: 'ellipsis',
          },
        })
      },
    },
    {
      name: "user_role", label: "User Role", options: {
        filter: true, sort: true, customBodyRender: (value) => (<div style={{
          color: "#0265DC", fontWeight: '500', fontSize: '12px', whiteSpace: 'nowrap',
          overflow: 'hidden',
          textOverflow: 'ellipsis',
        }}>{value}</div>)
      }
    },
    {
      name: "status",
      label: "Status",
      options: {
        filter: true, sort: true,
        customBodyRender: (value) => {
          let backgroundColor = 'transparent';
          let color = 'black';
          let circleBackgroundColor = 'black'
          if (value === 'Await Approval') {
            backgroundColor = '#EDEEFF';
            color = '#5258E4';
            circleBackgroundColor = '#5258E4';
          } else if (value === 'Leave Approved') {
            backgroundColor = '#CEF8E0';
            color = '#007A7D';
            circleBackgroundColor = '#007A7D';
          } else if (value === 'Rejected') {
            backgroundColor = '#FFEBE7';
            color = '#D31510';
            circleBackgroundColor = '#D31510';
          } else if (value === 'Cancelled') {
            backgroundColor = '#E1E3E6';
            color = '#414346';
            circleBackgroundColor = '#414346';
          }
          return (
            <div style={{ backgroundColor, color, width: 'fit-content' }} className={classes.StatusContainer}><div className={classes.circlePoint} style={{ backgroundColor: circleBackgroundColor }}></div>{value}</div>
          )
        }
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
