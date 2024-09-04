 <Switch
                                    onChange={(checked) => onMenuSelect(item.value, checked)} />
                                <div style={{ width: '5rem' }}>
                                    <Select
                                        className="crm-dropdown"
                                        style={{ width: '100%' }}
                                        defaultValue="Read"
                                        options={roleAccessOptions} />
                                </div>
