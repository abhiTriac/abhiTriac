  {Menus.map((item, index) => (
                        <div className={classes.container} key={index}>
                            <div className={classes.textContainer}>
                                {item.label}
                            </div>
                            <div className={classes.switchContainer}>
                                <Switch onChange={() =>  onMenuSelect(item.value) } />
                            </div>
                        </div>
                    ))}
