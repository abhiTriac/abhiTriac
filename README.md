import React, { useState } from 'react';
import MUIDataTable from 'mui-datatables';
import { createTheme, ThemeProvider, styled } from '@mui/material/styles';
import { CssBaseline, Chip } from '@mui/material';

const theme = createTheme();

const CustomChip = styled(Chip)(({ theme }) => ({
  width: '11.25rem',
  backgroundColor: '#ffffff',
  border: '1px solid #004b98',
  marginBottom: '1rem',
  '& .MuiChip-deleteIcon': {
    position: 'relative',
    bottom: '1rem',
    left: '3.8rem',
    color: '#004b98',
  },
}));

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
      <CssBaseline />
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
      {/* Use CustomChip component if you have Chip elements */}
    </ThemeProvider>
  );
};

export default CustomerTable;
