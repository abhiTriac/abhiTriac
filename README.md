- 👋 Hi, I’m @abhiTriac
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
abhiTriac/abhiTriac is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->



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
  
