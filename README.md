import React, { useState } from 'react';
import MUIDataTable from 'mui-datatables';
import { makeStyles, ThemeProvider, createTheme } from '@material-ui/core/styles';

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

  const theme = createTheme({
    components: {
      MuiToolbar: {
        styleOverrides: {
          root: {
            display: 'flex',
            alignItems: 'center',
            justifyContent: 'flex-end',
            gap: '0.5rem',
          },
        },
      },
    },
  });

  const options = {
    filterType: 'none',
    selectableRows: 'none',
    print: false,
    download: false,
    customToolbar: () => {
      return <CustomToolbar showAddCusSet={setShowAddCusSet} />;
    },
  };

  return (
    <ThemeProvider theme={theme}>
      <MUIDataTable
        title={
          <div style={{ display: 'flex', fontSize: '14px', fontWeight: '600', color: '#1C1C1C' }}>
            Customer List
          </div>
        }
        data={accounts}
        columns={columns}
        className={classes.tableHeader}
        options={options}
      />
    </ThemeProvider>
  );
};

export default CustomerTable;
