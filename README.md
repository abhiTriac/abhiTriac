 const [selectedRoles, setSelectedRoles] = useState({});
    // State to hold checked items
    const [checkedItems, setCheckedItems] = useState({});

    // Handle checkbox change
    const handleCheckBoxChange = (itemValue) => {
        setCheckedItems(prev => ({
            ...prev,
            [itemValue]: !prev[itemValue]
        }));
    };

    // Handle role change
    const handleRoleChange = (itemValue, newValue) => {
        setSelectedRoles(prev => ({
            ...prev,
            [itemValue]: newValue
        }));
    };

    // Generate the final output array
    const getOutputArray = () => {
        return customize_tab
            .filter(item => checkedItems[item.value])
            .map(item => ({
                value: item.value,
                access: selectedRoles[item.value] || 'read' // Default to "read" if no role selected
            }));
    };

    return (
        <div>
            {customize_tab.map((item, index) => (
                <div style={{ display: 'flex', gap: "0.5rem", justifyContent: "space-between" }} key={index}>
                    <div style={{ display: "flex" }}>
                        <input
                            type="checkbox"
                            checked={!!checkedItems[item.value]}
                            onChange={() => handleCheckBoxChange(item.value)}
                        />
                        <label className="form-label">
                            {item.label}
                        </label>
                    </div>
                    <div>
                        <Select
                            className="crm-dropdown"
                            style={{ width: '100%' }}
                            defaultValue="read"
                            value={selectedRoles[item.value] || "read"}
                            onChange={(value) => handleRoleChange(item.value, value)}
                            options={roleAccessOptions}
                        />
                    </div>
                </div>
            ))}

            {/* This button or function can be used to get the output array */}
            <button onClick={() => console.log(getOutputArray())}>
                Get Output Array
            </button>
        </div>
    );
};
