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
 let arr = ['sales']
    const onMenuSelect = (value, checked) => {
        console.log("value", value);
        console.log("checked", checked);
        if (checked == true) {
            arr.push(value)
        }
        else {
            const index = arr.indexOf(value);
            if (index > -1) {
                arr.splice(index, 1)
            }
        }
        // add_access_tabs_set(arr)
        console.log("arr", arr);
        console.log("add_access_tabs", add_access_tabs);
    }
