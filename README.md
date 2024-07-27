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


import React, { useState } from 'react';
import MUIDataTable from "mui-datatables";
import { makeStyles } from '@material-ui/core/styles';
import { MuiThemeProvider, createMuiTheme } from '@material-ui/core/styles';

const useStyles = makeStyles((theme) => ({
  toolbarActions: {
    display: 'flex',
    alignItems: 'center',
    justifyContent: 'flex-end',
    gap: '0.5rem',
    width: '100%',
  },
  addButton: {
    marginLeft: 'auto',
  },
}));

const CustomToolbar = ({ showAddCusSet }) => {
  const classes = useStyles();
  return (
    <div className={classes.toolbarActions}>
      <button className={classes.addButton} onClick={() => showAddCusSet(true)}>Add New</button>
    </div>
  );
};

const CustomerTable = () => {
  const classes = useStyles();
  const [showAddCusSet, setShowAddCusSet] = useState(false);

  const theme = createMuiTheme({
    overrides: {
      MUIDataTableToolbar: {
        actions: {
          // Applying the custom styles using a class name
          '& .MuiButton-root': classes.toolbarActions,
        },
      },
    },
  });

  const options = {
    filterType: "none",
    selectableRows: "none",
    print: false,
    download: false,
    customToolbar: () => {
      return (
        <CustomToolbar showAddCusSet={setShowAddCusSet} />
      );
    },
  };

  return (
    <MuiThemeProvider theme={theme}>
      <MUIDataTable
        title={<div style={{ display: "flex", fontSize: '14px', fontWeight: "600", color: '#1C1C1C' }}>Customer List</div>}
        data={accounts}
        columns={columns}
        className={classes.tableHeader}
        options={options}
      />
    </MuiThemeProvider>
  );
};

export default CustomerTable;

