  const formatDate = (date) => {
        const year = date.getFullYear();
        const month = String(date.getMonth() + 1).padStart(2, '0'); // Months are 0-indexed
        const day = String(date.getDate()).padStart(2, '0');
        const hours = '00'; // Set hours to 00
        const minutes = '00'; // Set minutes to 00
        const seconds = '00'; // Set seconds to 00
    
        return `${year}-${month}-${day} ${hours}:${minutes}:${seconds}`;
    };
    
    let [formValues, formSetValues] = useState({
        pro_name: "",
        company_title: "",
        company_type: company_type,
        company_email: "",
        phone_no: phone_no,
        street_address: "",
        subscription_model: subscription_model,
        subscription_expiry: formatDate(subscription_expiry),
        total_branch_count: total_branch_count,
        total_user_count: total_user_count,
        total_admin_count: admin_limit,
        total_accountant_count: total_accountant_count,
        admin_name: "",
        admin_password: "",

    });
