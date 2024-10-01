<AutoComplete
    style={{ width: "100%" }}
    options={[
        {
            value: "AddNew",
            label: (
                <span className="addNewDropdown">
                    <img style={{ height: '0.8rem' }} src={createNew} alt="Add New" /> Add New
                </span>
            ),
            obj: null,
        },
        ...items.map((item) => ({
            value: item.display_text,
            label: item.display_text,
            obj: item,
        })),
    ]}
    onChange={handleChangeSelectTag}
    value={selected_tag_group?.display_text || (selected_tag_group?.value === "AddNew" ? "Add New" : "")}
    filterOption={(inputValue, option) => {
        if (option.value === "AddNew") {
            return false;
        }
        if (typeof option.label === 'string') {
            return option.label.toUpperCase().includes(inputValue.toUpperCase());
        }
        const textContent = option.label.props.children[1]; // Assuming text is the second child
        return textContent.toUpperCase().includes(inputValue.toUpperCase());
    }}
>
    <Input placeholder="Search Item" />
</AutoComplete>

const handleChangeSelectTag = (value, option) => {
    if (option.props.value === "AddNew") {
        show_add_tag_set(true);
        selected_tag_group_set(null);
    } else {
        // Update the selected tag group with the new value
        selected_tag_group_set(option.props.obj); // Assuming you want to set the entire object
    }
};
