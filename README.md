 if (option.props.value === "Add New") {
    // Navigate to the add new item page
    history.push('/add-new-item'); // Change this to your desired route
    return;
  }
options={[
    { value: "Add New", label: "Add New", obj: null }, // Add New option
    ...items.map((item) => ({
      value: item.display_text,
      label: item.display_text,
      obj: item,
    })),
  ]}
