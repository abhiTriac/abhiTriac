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
