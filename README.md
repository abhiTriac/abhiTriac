 const menuData = [
    {
      key: "Dashboard",
      label: "Dashboard",
      icon: <img src={dashboardIcon} alt="dashboard" className="menu-icon" />,
      link: "/dashboard",
    },
    {
      key: "sales",
      label: "Sales",
      icon: <img src={salesIcon} className="menu-icon" alt="Sales" />,
      children: [
        {
          key: "sales_entry",
          label: "Sales Entry",
          link: "/sales/sales-entry",
        },
        {
          key: "customer_entry",
          label: "Customer Entry",
          link: "/sales/customer-entry",
        },
        {
          key: "sales_return_entry",
          label: "Sales Return Entry",
          link: "/sales/sales-return-entry",
        },
        {
          key: "replace_entry",
          label: "Replace Entry",
          link: "/sales/product-replace",
        },
        {
          key: "view_sales_voucher",
          label: "view Sales Voucher",
          link: "/sales/view-sales-voucher",
        },
        {
          key: "view_sales_return_voucher",
          label: "View Sales Return Voucher",
          link: "/sales/view-sales-return-voucher",
        },
        {
          key: "sales_record",
          label: "Sales Record",
          link: "/sales/sales-record",
        }, {
          key: "sales_return_record",
          label: "Sales Return Record",
          link: "/sales/sales-return-record",
        }, {
          key: "replace_record",
          label: "Replace Record",
          link: "/sales/product-replace-record",
        },
      ],
    },
    {
      key: "pos",
      label: "POS",
      icon: <img src={posIcon} alt="POS" className="svgIcon" style={{ color: 'white', }} />,
      link: "/pos/pos-entry",
    },
    {
      key: "quotation",
      label: "Quotation",
      icon: <img src={quotationIcon} alt="quotationIcon" className="menu-icon" />,
      children: [
        {
          key: "quotation_entry",
          label: "Quotation Entry",
          link: "/quotation/quotation-entry",
        },
        {
          key: "quotation_record",
          label: "Quotation Record",
          link: "/quotation/quotation-record",
        },
      ],
    }, {
      key: "order",
      label: "Order",
      icon: <img src={orderIcon} alt="orderIcon" className="menu-icon" />,
      children: [
        {
          key: "sales_order_entry",
          label: "Sales Order Entry",
          link: "/order/sales-order-entry",
        },
        {
          key: "purchase_order_entry",
          label: "Purchase Order Entry",
          link: "/order/purchase-order-entry",
        },
        {
          key: "sales_order_voucher",
          label: "Sales Order Voucher",
          link: "/order/view-sales-order-voucher",
        },
        {
          key: "purchase_order_voucher",
          label: "Purchase Order Vouchers",
          link: "/order/view-purchase-order-voucher",
        },
        {
          key: "purchase_order_record",
          label: "Purchase Order Record",
          link: "/order/purchase-order-record",
        },
        {
          key: "sales_order_record",
          label: "Sales Order Record",
          link: "/order/sales-order-record",
        },
      ],
    },
    {
      key: "service",
      label: "Service",
      icon: <img src={serviceIcon} alt="serviceIcon" className="menu-icon" />,
      children: [
        {
          key: "service_entry",
          label: "Service Entry",
          link: "/service/service-entry",
        },
        {
          key: "service_expense_entry",
          label: "Service Expense Entry",
          link: "/service/service-expense-entry",
        },
        {
          key: "service_voucher",
          label: "View Service Vouchers",
          link: "/service/view-service-vouchers",
        },
        {
          key: "service_expense_voucher",
          label: " View Service Expense Vouchers",
          link: "/service/view-service-expense-vouchers",
        },
        {
          key: "service_record",
          label: "Service Record",
          link: "/service/service-record",
        },
        {
          key: "service_expense_record",
          label: "Service Expense Record",
          link: "/service/service-expense-record",
        },
      ],
    },
    {
      key: "purchase",
      label: "Purchase",
      icon: <img src={purchaseIcon} alt="purchase" className="menu-icon" />,
      children: [
        {
          key: "purchase_entry",
          label: "Purchase Entry",
          link: "/purchase/purchase-entry",
        },
        {
          key: "supplier_entry",
          label: "Supplier Entry",
          link: "/purchase/supplier-entry",
        },
        {
          key: "purchase_return",
          label: "Purchase Return Entry",
          link: "/purchase/purchase-return-entry",
        },
        {
          key: "purchase_voucher",
          label: "View Purchase Vouchers",
          link: "/purchase/view-purchase-voucher",
        },
        {
          key: "purchase_return_voucher",
          label: "View Purchase Return Vouchers",
          link: "/purchase/view-purchase-return-voucher",
        },
        {
          key: "purchase_record",
          label: "Purchase Record",
          link: "/purchase/purchase-record",
        },
        {
          key: "purchase_return_record",
          label: "Purchase Return Record",
          link: "/purchase/purchase-return-record",
        },

      ]
    },
    {
      key: "manufacturing",
      label: "Manufacturing",
      icon: <img src={manufactureIcon} alt="manufacturing" className="svgIcon" />,
      children: [
        {
          key: "manufacturing_entry",
          label: "Manufacturing Journal Entry",
          link: "/manufacturing/manufacturing-journal-entry",
        },
        {
          key: "manufacturing_voucher",
          label: "Manufacturing Journal Voucher",
          link: "/manufacturing/view-manufacturing-voucher",
        }, {
          key: "manufacturing_record",
          label: "Manufacturing Journal Record",
          link: "/manufacturing/manufacturing-record",
        },
      ],
    },
    {
      key: "inventory",
      label: "Inventory",
      icon: <img src={inventryIcon} alt="inventory" className="svgIcon" />,
      children: [
        {
          key: "item_stock_report",
          label: "Item Stock Report",
          link: "/inventory/item-stock-report",
        },
        {
          key: "item_ledger",
          label: "Item Ledger",
          link: "/inventory/item-ledger",
        },
        {
          key: "transfer_entry",
          label: "Transfer Entry",
          link: "/inventory/transfer-entry",
        },
        {
          key: "item_adjustment_entry",
          label: "Item Adjustment Entry",
          link: "/inventory/item-adjustment",
        },
        {
          key: "adjustment_record",
          label: "Adjustment Record",
          link: "/inventory/adjustment-record",
        },
        {
          key: "transfer_record",
          label: "Transfer Record",
          link: "/inventory/transfer-record",
        }, {
          key: "transfer_pending_record",
          label: "Transfer Pending Record",
          link: "/inventory/transfer-pending-record",
        },
        {
          key: "transfer_receive_record",
          label: "Transfer Receive Record",
          link: "/inventory/transfer-receive-record",
        },
      ]
    },
    {
      key: "accounts",
      label: "Accounts",
      icon: <img src={accountsIcon} alt="Accounts" className="menu-icon" />,
      children: [
        {
          key: "debtor_receipt",
          label: "Customer Receipt Entry",
          link: "/accounts/debitor-receipt-entry",
        },
        {
          key: "creditor_payment",
          label: "Supplier Payment Entry",
          link: "/accounts/creditor-payment-entry",
        },
        {
          key: "expense_entry",
          label: "Expense Entry",
          link: "/accounts/expense-entry",
        },
        {
          key: "expense_recognition_entry",
          label: "Expense Recognition Entry",
          link: "/accounts/expense-recognition-entry",
        },
        {
          key: "income_entry",
          label: "Income Entry",
          link: "/accounts/income-entry",
        },
        {
          key: "contra_entry",
          label: "Contra/ Single Entry",
          link: "/accounts/contra-entry",
        }, {
          key: "advance_transaction_entry",
          label: "Advance Transaction Entry",
          link: "/accounts/advance-tran-entry",
        },
        {
          key: "journal_entry",
          label: "Journal/ Double Entry",
          link: "/accounts/journal-entry",
        },
        {
          key: "branch_tran",
          label: "Branch Transaction Entry",
          link: "/accounts/branch-tran",
        },
        {
          key: "account_entry",
          label: "Account Entry",
          link: "/accounts/account-entry",
        },
        {
          key: "location_entry",
          label: "Location Entry",
          link: "/accounts/location-manage",
        },
      ]
    },
    {
      key: "hrpayroll",
      label: "HR & Payroll",
      icon: <img src={hrIcon} alt="Payroll" className="svgIcon" />,
      children: [
        {
          key: "salary_payment",
          label: "Salary Payment Entry",
          link: "/hrpayroll/salary-payment-entry",
        },
        {
          key: "attendance_entry",
          label: "Attendance Entry",
          link: "/hrpayroll/attendance-entry",
        },
        {
          key: "attendance_overview",
          label: "Attendance Overview",
          link: "/hrpayroll/attendance-overview",
        },
        {
          key: "employee_entry",
          label: "Employee Entry",
          link: "/hrpayroll/employee-entry",
        },
        {
          key: "department_entry",
          label: "Department Entry",
          link: "/hrpayroll/department-entry",
        },
        {
          key: "designation_entry",
          label: "Designation Entry",
          link: "/hrpayroll/designation-entry",
        }, {
          key: "salary_report",
          label: "Salary Payment Report",
          link: "/hrpayroll/salary-report",
        },
        {
          key: "monthly_salary_report",
          label: "Monthly salary Report",
          link: "/hrpayroll/monthly-salary-report",
        },
      ]
    }, {
      key: "reports",
      label: "Reports",
      icon: <img src={reportIcon} alt="Reports" className="svgIcon" />,
      link: "/reports",
    },
    {
      key: "crm",
      label: "CRM",
      icon: <img src={crmIcon} alt="CRM" className="menu-icon" />,
      children: [
        {
          key: "customer_entry",
          label: "Customer Entry",
          link: "/crm/customer-entry",
        },
        {
          key: "pending_customer_list",
          label: "Pending Customer List",
          link: "/crm/customer-pending-list",
        }, {
          key: "approved_customer_list",
          label: "Approved Customer List",
          link: "/crm/customer-approved-list",
        },
        {
          key: "rejected_customer_list",
          label: "Rejected Customer List",
          link: "/crm/customer-rejected-list",
        },
        {
          key: "employee_wise_customer_list",
          label: "Employee Wise Customer List",
          link: "/crm/user-wise-customer-report",
        },
      ],
    },
    {
      key: "settings",
      label: "Settings",
      icon: <img src={settingIcon} alt="Settings" className="menu-icon" />,
      link: "/settings",
    },
  ];
