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
              '[class*="MuiTableCell-root-"]': {
                padding: '0',
                paddingLeft: '1rem'
              },
              '[class*="MuiPaper-elevation4-"]': {
                boxShadow: 'none',
              },
              '[class*=" MUIDataTableHeadCell-"]': {
                textTransform:'uppercase',
              },
              '@media (max-width: 960px)': {
                '[class*="MUIDataTableBodyCell-stackedCommon-"]': {
                  height: '40px'
                },
                '[class*="MuiToolbar-gutters-"]': {
                  paddingLeft: '0',
                  paddingRight: '0'
                },
              }
            }}
          />
          <div className={classes.tableContainer} >
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
              title={<div style={{ display: "flex", fontSize: '14px', fontWeight: "600", color: '#1C1C1C' }}>Department List</div>}
              data={departments}
              columns={columns}
              className={classes.tableHeader}
              options={options}
            />
          </div>
        </ThemeProvider>
