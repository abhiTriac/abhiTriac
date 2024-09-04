  const [checkedItems, setCheckedItems] = useState(() => {
        const initialArr = ['sales'];
        const initialChecked = {};
        Menus.forEach(item => {
            initialChecked[item.value] = initialArr.includes(item.value);
        });
        return initialChecked;
    });

    // Handle switch toggle
    const onMenuSelect = (value, checked) => {
        setCheckedItems(prevState => {
            const newState = { ...prevState, [value]: checked };
            const updatedArr = Object.keys(newState).filter(key => newState[key]);
            console.log("value", value);
            console.log("checked", checked);
            console.log("arr", updatedArr);
            // Perform any additional actions with updatedArr
            // add_access_tabs_set(updatedArr);
            return newState;
        });
    };
