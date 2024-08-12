     <Grid item xs={12} sm={1}></Grid>                   
                      <Grid item xs={12} sm={3}>
                        <label className="form-label"> Amount</label>
                        <InputNumber
                          ref={tran_amount_ref}
                          onKeyDown={(e) =>
                            e.key === "Enter" ? addPay() : true
                          }
                          className={classes.fullWidth}
                          placeholder="Amount"
                          name="tran_amount"
                          value={tran_amount}
                          style={{
                            border: "1px solid #d9d9d9",
                            borderRadius: "4px",
                          }}
                          onChange={(value) => tran_amount_set(value)}
                        />
                      </Grid>
                      <Grid item xs={12} sm={1}></Grid>
                      <Grid item xs={12} sm={2}>
                        <label className="form-label">
                          {" "}
                          <span className="form-span">*</span>
                        </label>
                        <Button
                          type="primary"
                          onClick={() => addPay()}
                          style={{ width: "100%" }}
                        >
                          Add{" "}
                        </Button>
                      </Grid>
                    </Grid>

                    <Grid container>
                      <div style={{ width: "100%" }}>
                        <Table
                          dataSource={payCart}
                          pagination={false}
                          rowKey="index"
                          scroll={{ x: "min-content" }}
                          summary={() => (
                            <Table.Summary.Row>
                              <Table.Summary.Cell index={0} colSpan={2}>
                                <strong>Total Paid :</strong>
                              </Table.Summary.Cell>
                              <Table.Summary.Cell index={1}>
                                <strong>
                                  {format(
                                    _.sumBy(payCart, (pay) =>
                                      Number(pay.tran_amount)
                                    ).toFixed(2)
                                  )}
                                </strong>
                              </Table.Summary.Cell>
                              <Table.Summary.Cell
                                index={2}
                              ></Table.Summary.Cell>
                            </Table.Summary.Row>
                          )}
                        >
                          <Table.Column
                            title="NO."
                            dataIndex="index"
                            key="index"
                            render={(text, record, index) => index + 1}
                            align="left"
                            width="5%"
                          />
                          <Table.Column
                            title="Received Into Account"
                            dataIndex="to_acc_name"
                            key="to_acc_name"
                            align="left"
                            width="50%"
                          />
                          <Table.Column
                            title="Amount"
                            dataIndex="tran_amount"
                            key="tran_amount"
                            width="27%"
                            render={(text) =>
                              format(parseFloat(text).toFixed(2))
                            }
                          />
                          <Table.Column
                            title="Action"
                            key="action"
                            width="18%"
                            render={(text, record, index) => (
                              <>
                                <img src={EditIcon}
                                  style={{
                                    cursor: "pointer",
                                    color: "#2e482e",
                                    marginLeft: "2px",
                                  }}
                                  onClick={() => editPayFromCart(record, index)}
                                />
                                <span style={{ width: "2px" }}> </span>
                                <img src={deleteIcon}
                                  style={{
                                    cursor: "pointer",
                                    color: "#582727",
                                    marginLeft: "2px",
                                  }}
                                  onClick={() => removePayFromCart(index, record)}
                                />
                              </>
                            )}
                          />
                        </Table>
                      </div>
                    </Grid>
