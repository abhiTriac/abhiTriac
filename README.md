const useStyles = makeStyles((theme) => ({


  paper: {
    padding: "2rem 2rem",
    textAlign: "center",
    color: theme.palette.text.secondary,
    boxShadow: 'none'
  },
  pageEntryLabel: {
    margin: "0px",
    padding: "0px",
    marginTop: "-11px",
    textAlign: "left",
    marginLeft: "0px",
    marginBottom: "5px",
    color: "#391f22",
    fontWeight: "600",
    fontSize: " 20px",
    lineHeight: "32px",
    display: "flex",
    gap: "1rem",
  },

}));

  <ThemeProvider theme={theme}>
          <CssBaseline />
          <GlobalStyles
            styles={{
              '[class*="MuiChip-root"]': {
                width: '11.25rem !important',
                backgroundColor: '#ffffff !important',
                border: '1px solid #004b98 !important',
                marginBottom: '1rem !important',
              },
              '[class*="MuiChip-deleteIcon"]': {
                position: 'relative !important',
                bottom: '1rem !important',
                left: '3.8rem !important',
                color: '#004b98 !important',
              },
              '[class*="MUIDataTableToolbar-actions-"]': {
                display: 'flex',
                alignItems: 'center',
                justifyContent: 'flex-end',
                gap: '0.5rem',
              },
              '[class*="MUIDataTableHeadCell-sortAction-"]': {
                alignItems: 'center',
              },
              '[class*="MuiToolbar-gutters-"]': {
                paddingLeft: '1rem'
              },
              '[class*="MuiPaper-elevation4-"]': {
                boxShadow: 'none',
              },
            }}
          />
          <div style={{ marginTop: "20px", backgroundColor: '#F7F9FB', boxShadow: 'none' }}>
            <div className={classes.tableHeader}>
              <div className={classes.filterList}>
                {columns.filter(column => column.options.filter).map((column, index) => (
                  <div key={index}>
                    {column.options?.customFilterListRender ? column.options.customFilterListRender([]) : null}
                  </div>
                ))}
              </div>
            </div>
            <MUIDataTable
              title={<div style={{ display: "flex", fontSize: '14px', fontWeight: "600", color: '#1C1C1C' }}>Customer List</div>}
              data={accounts}
              columns={columns}
              className={classes.tableHeader}
              options={options}
            />
          </div>
        </ThemeProvider>
