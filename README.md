  const columns = [
        { name: "id", options: { display: "excluded" } },
        {
            name: "NO.",
            options: {
                filter: false,
                sort: false,
                customBodyRender: (value, tableMeta) => {
                    return <p>{parseFloat(tableMeta.rowIndex) + 1}</p>;
                },
            },
            headerStyle: {
                textAlign: "left",
            },
        },
        {
            name: "pro_name",
            label: "Company",
            options: { filter: true, sort: true },
        },
        {
            name: "total_branch_count",
            label: "Branch Count",
            options: { filter: true, sort: true },
        },
        {
            name: "used_branch",
            label: "Used Branch",
            options: { filter: true, sort: true },
        },
        {
            name: "total_user_count",
            label: "Total Users",
            options: { filter: true, sort: true },
        },
        {
            name: "branch_count",
            label: "Used Users",
            options: { filter: true, sort: true },
        },
        {
            name: "subscription_expiry",
            label: "Plan Expiry",
            options: { filter: true, sort: true },
        },


    ];
