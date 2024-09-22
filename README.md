  filterOption={(inputValue, option) => {
    // Check if option.label is a string or a React element
    if (typeof option.label === 'string') {
      return option.label.toUpperCase().includes(inputValue.toUpperCase());
    }
    // If it's a React element, extract the text
    const textContent = option.label.props.children[1]; // Assuming text is the second child
    return textContent.toUpperCase().includes(inputValue.toUpperCase());
  }}
