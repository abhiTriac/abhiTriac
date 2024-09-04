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
const Menus = [
        { label: 'Dashboard', value: 'dashboard' },
        { label: 'Sales', value: 'sales' },
        { label: 'POS', value: 'pos' },
        { label: 'Quotation', value: 'quotation' },
        { label: 'Order', value: 'order' },
        { label: 'Service', value: 'service' },
        { label: 'Purchase', value: 'purchase' },
        { label: 'Manufacturing', value: 'manufacturing' },
        { label: 'Inventry', value: 'inventry' },
        { label: 'Accounts', value: 'accounts' },
        { label: 'HR&Payroll', value: 'hrpayroll' },
        { label: 'Reports', value: 'reports' },
        { label: 'CRM', value: 'crm' },
        { label: 'Settings', value: 'settings' },
    ]

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
    let [checked_item, checked_item_set] = useState(() => {
        const array = ['sales'];
        const initialCheked = {};
        Menus.forEach(item => {
            initialCheked[item.value] = arr.includes(item.value)
        })
        return initialCheked
    })
