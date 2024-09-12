 const [selectedRoles, setSelectedRoles] = useState({});
    const [checked_Items, setChecked_Items] = useState({});
  const getAccessType = async () => {
        await axios
            .post(`${BACKEND_API_URL}/api/get-access-type`,
                { role_id: 1 }, {
                headers: { "auth-token": authInfo.token },
            })
            .then((res) => {
                const data = res.data;
                const initialData = data.map(item => ({
                    value: item.access,
                    access_type: item.access_type
                }));
                const initialSelectedRoles = {};
                const initialCheckedItem = {};
                console.log("initialData", initialData);
                initialData.forEach(item => {
                    initialCheckedItem[item.value] = true;
                    initialSelectedRoles[item.value] = item.access_type;
                })
                setIntialTab(initialData)
                setSelectedRoles(initialSelectedRoles)
                setChecked_Items(initialCheckedItem)
                console.log('res acess', res.data);
            });
    };
   const handleCheckBoxChange = (itemValue) => {

        setChecked_Items(prev => ({
            ...prev,
            [itemValue]: !prev[itemValue]
        }));
     
    };

    const handleRoleChange = (itemValue, newValue) => {
        setSelectedRoles(prev => ({
            ...prev,
            [itemValue]: newValue
        }));
    
    };

    const getOutputArray = () => {
        return customize_tab
            .filter(item => AddChecked_Items[item.value])
            .map(item => ({
                value: item.value,
                access: addSelectedRoles[item.value] || 'read',
                tab: select_tab
            }));
    };

    const handleCustomSettingChange = () => {
        const data = getOutputArray()

        console.log("data", data);

        select_tab_set("")
        customize_data_array_set(prevState => [...prevState, data])
        // const array = customize_data_array.flat();
        const array = customize_data_array.flat();
        console.log("customize data array", array);
        const map = new Map();

        array.forEach(item => {
            const key = JSON.stringify(item);
            if (!map.has(key)) {
                map.set(key, item);
            }
        });
        console.log("array", Array.from(map.values()));
        user_customize_modal_set(false)
    }
  <Grid item xs={12} sm={12}>
                            {customize_tab.map((item, index) => (
                                <div style={{ display: 'flex', gap: "0.5rem", justifyContent: "space-between" }} key={index}>
                                    <div style={{ display: "flex" }}>
                                        <input
                                            type="checkbox"
                                            checked={!!checked_Items[item.value]}
                                            onChange={() => handleCheckBoxChange(item.value)
                                            }
                                        />
                                        <label className="form-label">
                                            {" "}
                                            {item.label}

                                        </label>
                                    </div>
                                    {/* {checked_Items[item.value] && ( */}
                                    <div style={{ width: '5rem' }}>
                                        <Select
                                            className="crm-dropdown"
                                            style={{ width: '100%' }}
                                            value={selectedRoles[item.value] || "read"}
                                            onChange={(value) => handleRoleChange(item.value, value)}
                                            options={roleAccessOptions} />
                                    </div>
                                    {/* )} */}

                                </div>
                            ))}

                        </Grid>
