import React from 'react';
import MUIDataTable from 'mui-datatables';
import { makeStyles } from '@mui/styles';
import ArrowUpwardIcon from '@mui/icons-material/ArrowUpward';
import ArrowDownwardIcon from '@mui/icons-material/ArrowDownward';

const useStyles = makeStyles({
  sortIcon: {
    '& path': {
      fill: 'red', // Change the color of the sort arrow
    },
  },
});

const MyTable = ({ accounts }) => {
  const classes = useStyles();

  const columns = [
    { name: "acc_id", options: { display: "excluded" } },
    {
      name: "acc_name",
      label: "Customer Name",
      options: {
        filter: true,
        sort: true,
        sortThirdClickReset: true,
      },
    },
    // Other columns...
  ];

  const options = {
    // Other options...
  };

  return (
    <MUIDataTable
      title="Customer List"
      data={accounts}
      columns={columns}
      options={options}
      components={{
        icons: {
          SortArrow: (props) => (
            props.direction === 'asc' ? <ArrowUpwardIcon className={classes.sortIcon} /> : <ArrowDownwardIcon className={classes.sortIcon} />
          ),
        },
      }}
    />
  );
};

export default MyTable;
