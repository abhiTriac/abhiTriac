 {Menus.map((item, index) => (
                        <div className={classes.container} key={index}>
                            <div className={classes.textContainer}>
                                {item.label}
                            </div>
                            <div className={classes.switchContainer}>
                                <Switch
                                    onChange={(checked) => onMenuSelect(item.value, checked)} />
                            </div>
                        </div>
                    ))}
