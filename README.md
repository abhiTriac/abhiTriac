  const Menus = [
        { label: 'Dashboard', value: 'dashboard' },
        { label: 'Sales', value: 'sales' },
        { label: 'POS', value: 'pos' },
        { label: 'Quotation', value: 'quotation' },
        { label: 'Order', value: 'order' },
        { label: 'Service', value: 'service' },
        { label: 'Purchase', value: 'purchase' },
        { label: 'Manufacturing', value: 'manufacturing' },
        { label: 'Inventry', value: 'inventry' },
        { label: 'Accounts', value: 'accounts' },
        { label: 'HR&Payroll', value: 'hrpayroll' },
        { label: 'Reports', value: 'reports' },
        { label: 'CRM', value: 'crm' },
        { label: 'Settings', value: 'settings' },
    ]
  {Menus.map((item, index) => (
                        <div className={classes.container} key={index}>
                            <div className={classes.textContainer}>
                                {item.label}
                            </div>
                            <div className={classes.switchContainer}>
                                <Switch onChange={() =>  onMenuSelect(item.value) } />
                            </div>
                        </div>
                    ))}
