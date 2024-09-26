  if (!values.pro_name) {
        errors.pro_name = "Product name is required.";
    }
    if (!values.company_title) {
        errors.company_title = "Company title is required.";
    }
    if (!values.company_email) {
        errors.company_email = "Company email is required.";
    } else if (!/\S+@\S+\.\S+/.test(values.company_email)) {
        errors.company_email = "Email format is invalid.";
    }
    if (values.total_branch_count < 0) {
        errors.total_branch_count = "Total branch count must be non-negative.";
    }
