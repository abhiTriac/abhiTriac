Can't perform a React state update on an unmounted component. This is a no-op, but it indicates a memory leak in your application. To fix, cancel all subscriptions and asynchronous tasks in a useEffect cleanup function.
    in Overflow (created by ForwardRef)

const CustomToolbar = (props) => {
    return (
      <>
        <button className="add-button" onClick={() => { showAddCusSet(true) }}>Add New</button>
      </>

    );
  };


  const options = {
    filterType: "none",
    selectableRows: "none",
    print: false,
    download: false,
    customToolbar: () => {
      return (
        <CustomToolbar />
      );
    },
  };

    <MUIDataTable
              title={<div style={{ display: "flex", fontSize: '14px', fontWeight: "600", color: '#1C1C1C' }}>Customer List</div>}
              data={accounts}
              columns={columns}
              className={classes.tableHeader}
              options={options}
            />
