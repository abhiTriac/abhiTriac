import React, { useState } from 'react';
import MUIDataTable from 'mui-datatables';
import { createTheme, ThemeProvider } from '@material-ui/core/styles';
import { GlobalStyles } from '@mui/system';

const theme = createTheme();

const CustomToolbar = ({ showAddCusSet }) => {
  return (
    <button className="add-button" onClick={() => showAddCusSet(true)}>
      Add New
    </button>
  );
};

const CustomerTable = () => {
  const [showAddCusSet, setShowAddCusSet] = useState(false);

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
      <GlobalStyles
        styles={{
          '[class*="MUIDataTableToolbar-actions-"]': {
            display: 'flex',
            alignItems: 'center',
            justifyContent: 'flex-end',
            gap: '0.5rem',
          },
          '.add-button': {
            marginLeft: 'auto',
          },
        }}
      />
      <MUIDataTable
        title={
          <div style={{ display: 'flex', fontSize: '14px', fontWeight: '600', color: '#1C1C1C' }}>
            Customer List
          </div>
        }
        data={accounts}
        columns={columns}
        options={options}
      />
    </ThemeProvider>
  );
};

export default CustomerTable;
