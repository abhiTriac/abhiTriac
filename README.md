{customize_tab.map((item, index) => (
                                <div style={{ display: 'flex', gap: "0.5rem" }} key={index}>
                                    <input
                                        type="checkbox"
                                        // checked={true}
                                        onChange={() => {
                                            console.log(item);
                                        }}
                                    />
                                    <label className="form-label">
                                        {" "}
                                        {item.label}

                                    </label>
                                </div>
                            ))}
