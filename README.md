<Table
                dataSource={itemCart}
                columns={tableColumns}
                pagination={false}
                scroll={{ x: "min-content" }}
                rowKey="item_id"
                rowClassName={(record, index) =>
                  index === sale_ind_id ? classes.highlightedRow : ""
                }
              />
