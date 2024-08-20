  <Card style={{ height: "100%" }} className={classes.cardBody}>
                    <div className="main-header-container">
                      <div
                        className={
                          product_state === 1
                            ? "main-header-active"
                            : "main-header"
                        }
                        onClick={() => {
                          product_state_set(0);
                        }}
                      >
                        MOST SELLING PRODUCTS
                      </div>
                      |
                      <div
                        className={
                          product_state === 1
                            ? "main-header"
                            : "main-header-active"
                        }
                        onClick={() => {
                          product_state_set(1);
                        }}
                      >
                        LEAST SELLING PRODUCTS
                      </div>
                    </div>
                    <ResponsiveContainer width="100%" height={300}>
                      <BarChart
                        data={products_data}
                        margin={{
                          top: 5,
                          right: 30,
                          left: -20,
                          bottom: 5,
                        }}
                      >
                        <XAxis
                          dataKey="name"
                          axisLine={false}
                          tickLine={false}
                          padding={{ left: 0, right: 20 }}
                        ></XAxis>
                        <YAxis axisLine={false} tickLine={false}
                          padding={{ top: 20, bottom: 15 }}
                        ></YAxis>

                        <Bar
                          dataKey="value"
                          fill="#8884d8"
                          radius={8}
                          barSize={38}
                        >
                          {products_data.map((entry, index) => (
                            <Cell
                              key={`cell-${index}`}
                              fill={COLORS[index % COLORS.length]}
                            />
                          ))}
                          <LabelList
                            dataKey="value"
                            content={renderCustomizedLabel}
                          />
                        </Bar>
                      </BarChart>
                    </ResponsiveContainer>
                  </Card>
