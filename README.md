 {customize_tab.map((item, index) => (
                                <div style={{ display: 'flex', gap: "0.5rem", justifyContent: "space-between" }} key={index}>
                                    <div style={{ display: "flex" }}>
                                        <input
                                            type="checkbox"
                                            // checked={!!checked_item[item.value]}
                                            onChange={() => handleCheckBoxChange(item.value)
                                            }
                                        />
                                        <label className="form-label">
                                            {" "}
                                            {item.label}

                                        </label>
                                    </div>
                                    <div >
                                        <Select
                                            className="crm-dropdown"
                                            style={{ width: '100%' }}
                                            defaultValue="Read"
                                            value={selected_role}
                                            onChange={handleRoleChange}
                                            options={roleAccessOptions} />
                                    </div>
                                </div>
                            ))}
 let [checked_item, checked_item_set] = useState({})
    let [selected_role, selected__role_set] = useState(roleAccessOptions[0])

    const customizeSettings = (item) => {
        console.log('item', item);
        user_customize_modal_set(true)
        customize_title_set(item.label)
        customize_tab_set(accessTabs(item.value))
        console.log("tab", customize_tab);
    }
    // handle check box change
    const handleCheckBoxChange = (value) => {
        checked_item_set(prevState => ({
            ...prevState,
            [value]: !prevState[value]
        }))
    }

    const handleRoleChange = (value) => {
        selected__role_set(value)
    }

    const roleCombineData = () => {
        return Object.keys(checkedItems).filter(key =>
            checked_item[key]).map(value =>
                ({ value, access: selected_role.value }))
    }

    const handleCustomSettingChange = () => {
        const data = roleCombineData
        console.log("data", data);
    }
