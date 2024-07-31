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
    const columns = [
    { name: "acc_id", options: { display: "excluded" } },
    {
      name: "Sl No.",
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
      name: "acc_name",
      label: (<div style={{ display: 'flex', alignItems: 'center' }}>Customer Name <img src={MinusCircleOutlined} /></div>),
      options: {
        filter: true, sort: true,
        // customBodyRender:(value)=>(
        //   <div style={{backgroundColor:'red' , width:'fit-content'}}>{value}</div>
        // )
      },
    },
    { name: "acc_code", label: "Code", options: { filter: true, sort: true } },
    {
      name: "party_type",
      label: "Type",
      options: { filter: true, sort: true },
    },
    {
      name: "institution_name",
      label: "Institution",
      options: {
        filter: true, sort: true,

      },
    },
    {
      name: "address",
      label: "Address",
      options: { filter: true, sort: true, },
    },
    {
      name: "contact_no",
      label: "Contact No",
      options: { filter: true, sort: true, display: "false" },
    },
    {
      name: "location_name",
      label: "Area",
      options: { filter: true, sort: true, display: "false" },
    },
    {
      name: "opening_balance",
      label: "Opening Due",
      options: { filter: true, sort: true, display: "false" },
    },
    {
      name: "user_full_name",
      label: "Entry By",
      options: { filter: true, sort: true, display: "false" },
    },
    {
      name: "credit_limit",
      label: "Credit Limit ",
      options: { filter: true, sort: true, display: "false" },
    },
    {
      name: "credit_Month",
      label: "Credit Month ",
      options: { filter: true, sort: true, display: "false" },
    },
    {
      name: "licence_no",
      label: "Licence No ",
      options: { filter: true, sort: true, display: "false" },
    },
    {
      name: "vat_no",
      label: "VAT No ",
      options: { filter: true, sort: true, display: "false" },
    },

    {
      name: "",
      options: {
        filter: false,
        sort: false,
        display: "true",
        customBodyRender: (value, tableMeta) => {
          return (
            <ActionOptions
              value={value}
              rowIndex={tableMeta.rowIndex}
              rowData={tableMeta.rowData}
            />
          );
        },
      },
      headerStyle: {
        textAlign: "left",
      },
    },
  ];


    <MUIDataTable
              title={<div style={{ display: "flex", fontSize: '14px', fontWeight: "600", color: '#1C1C1C' }}>Customer List</div>}
              data={accounts}
              columns={columns}
              className={classes.tableHeader}
              options={options}
            />

