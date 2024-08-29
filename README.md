class PrintAbleSection extends React.Component {
    constructor(props) {
        super(props);
    }

    state = {
        sales: [],
        institution: null,
        accDue: 0,
        printPad: "yes",
    };
    logo = ''

    componentDidMount() {
        this.getSalesOrder();
        this.setState({ institution: this.props.institution });
        this.logo = `${BACKEND_API_URL}/`
    }

    // pro_logo = `${BACKEND_API_URL}/`+ this.props.institution.pro_logo

    componentDidUpdate(prevProps, prevState) {
        if (prevProps.sale_id != this.props.sale_id) {
            this.getSalesOrder();
        }
    }

    getSalesOrder = async () => {
        let accId = null;
        await axios
            .post(
                `${BACKEND_API_URL}/api/get-sales-record-with-details`,
                { sale_id: this.props.sale_id, from: "voucher" },
                { headers: { "auth-token": this.props.authInfo.token } }
            )
            .then((res) => {
                if (res.data.length == 0) return false;

                // Detail Data to Product Cart - Start

                accId = res.data[0].acc_id;
                let itemCartData = res.data[0].details.map((item) => {
                    let serials = [];

                    serials = item.serials.split(",");
                    if (item.is_serial == "yes") {
                        serials = serials.map((slNo) => {
                            return { serial_number: slNo };
                        });
                    } else {
                        serials = [];
                    }

                    let updateItem = {
                        warehouse_id: item.warehouse_id,
                        warehouse_name: item.warehouse_name,
                        item_id: item.item_id,
                        item_name: item.item_name,
                        display_text: item.display_text,
                        is_serial: item.is_serial,
                        item_qty: item.item_qty,
                        item_rate: item.item_rate,
                        item_discount: item.item_discount,
                        item_discount_per: item.item_discount_per,
                        discount_acc_id: item.discount_acc_id,
                        discount_acc_name: item.discount_acc_name,
                        item_tax: item.item_tax,
                        item_tax_per: item.item_tax_per,
                        tax_acc_id: item.tax_acc_id,
                        tax_acc_name: item.tax_acc_name,
                        serials,
                        item_total: item.item_total,
                        retail_qty: item.retail_qty,
                        sale_qty: item.sale_qty,
                        sale_rate: item.sale_rate,
                        qty_display:
                            item.item_qty +
                            " " +
                            item.unit_symbol +
                            (item.conversion > 1
                                ? ", " + item.retail_qty + " " + item.base_unit_name
                                : ""),
                        done_qty_display:
                            item.done_item_qty +
                            " " +
                            item.unit_symbol +
                            (item.conversion > 1
                                ? ", " + item.done_retail_qty + " " + item.base_unit_name
                                : ""),
                        unit_symbol: item.unit_symbol,
                        base_unit_name: item.base_unit_name,
                        unit_name: item.unit_name,
                        conversion: item.conversion,
                        serial_note: item.serial_note,
                        narration: item.narration,
                    };
                    return updateItem;
                });

                res.data[0].details = itemCartData;

                this.setState({ sales: res.data[0] });
            });

        await axios
            .post(
                `${BACKEND_API_URL}/api/get-sundry-debitor-balance`,
                { customerId: accId },
                { headers: { "auth-token": this.props.authInfo.token } }
            )
            .then((res) => {
                if (res.data.accounts.length == 0) {
                    this.setState({ accDue: 0 });
                    return false;
                }
                this.setState({ accDue: res.data.accounts[0].balance });
            });
    };


    render() {
        let { sales, institution, accDue } = this.state;

        // let log = `${BACKEND_API_URL}` + institution.pro_logo
        console.log('state', institution);
        return (
            <div style={{ padding: "20px", paddingBottom: "0px" }}>
                {sales.length != 0 ? (
                    <>
                        <Grid container className={"invoice-title"}>
                            <Grid item xs={12} sm={12}>
                                <h3
                                    style={{
                                        textAlign: "center",
                                        margin: "0",
                                        padding: "0",
                                        marginTop: "11px",
                                    }}
                                >
                                    INVOICE
                                </h3>
                            </Grid>
                        </Grid>
                        <Grid
                            container
                            style={{
                                marginBottom: "5px",
                                fontSize: "12px",
                                color: "#222",
                                marginTop: "5px",
                            }}
                        >
                            <Grid item xs={6} sm={6}>
                                {/* <strong>Customer/ Debtor Code : </strong> <span>{ sales.acc_code }</span><br/> */}
                                <strong> Name : </strong> <span>{sales.acc_name}</span>
                                <br />
                                {/* <strong>Institution  : </strong> <span>{ sales.institution_name }</span><br/> */}
                                <strong> Address : </strong> <span>{sales.address}</span>
                                <br />
                                <strong> Contact No : </strong> <span>{sales.contact_no}</span>
                                <br />
                            </Grid>
                            <Grid item xs={6} sm={6} style={{ textAlign: "right" }}>
                                <strong>Invoice No : </strong>{" "}
                                <span>{sales.sale_voucher_no}</span>
                                <br />
                                <strong>Sales Date : </strong>{" "}
                                <span>
                                    {moment(sales.created_date).format(dateWithTimeFormat)}
                                </span>
                                <br />
                                <strong>Sales By : </strong> <span>{sales.user_full_name}</span>
                                <br />
                                {/* {sales.group_name !=  ''  ?<> <strong>Group Name  : </strong> <span>{ sales.group_name }</span> </> :""} <br/> */}
                            </Grid>
                        </Grid>

                        <Grid container className={"invoice-background"}>
                            <Grid item xs={12} sm={8}>
                                <h3
                                    style={{
                                        margin: "0",
                                        padding: "0",
                                        marginTop: "11px",
                                    }}
                                >
                                    INVOICE
                                </h3>
                                <div style={{ display: 'flex', gap: '2rem', flexDirection: "column", paddingTop: '2rem' }}>
                                    <div style={{ display: 'flex', justifyContent: 'space-between' }}>
                                        <div>
                                            <p><strong>
                                                DATE
                                            </strong>
                                            </p>
                                            <p>21/2/2024</p>
                                        </div>
                                        <div style={{ width: '35%' }}>
                                            <p>
                                                <strong>
                                                    INVOICE NO
                                                </strong></p>
                                            <p>INV/2024/001</p>
                                        </div>
                                    </div>
                                    <div style={{ display: 'flex', justifyContent: 'space-between' }}>
                                        <div>
                                            <p>
                                                <strong>
                                                    INVOICE TO
                                                </strong></p>
                                            <p><strong>
                                                Intertec System</strong></p>
                                            <p>
                                                Prime Tower, Floor 25, P.O. Box
                                            </p>
                                            <p>316996, Dubai, UAE</p>
                                            <p>anuja@gmail.com</p>
                                            <p>Kind Attn: Anuja Sethi</p>
                                        </div>
                                        <div style={{ width: '35%' }}>
                                            <p>
                                                <strong>
                                                    SHIP TO
                                                </strong></p>
                                            <p><strong>
                                                Intertec System</strong></p>
                                            <p>
                                                Prime Tower, Floor 25, P.O. Box
                                            </p>
                                            <p>316996, Dubai, UAE</p>
                                            <p>anuja@gmail.com</p>
                                            <p>Kind Attn: Anuja Sethi</p>
                                        </div>
                                    </div>
                                </div>
                            </Grid>
                            <Grid item xs={12} sm={4}>
                                <div style={{ display: 'flex', flexDirection: 'column', alignItems: 'flex-end' }}>
                                    <div>
                                        <div>
                                            {/* <img src={`${BACKEND_API_URL}/` + institution.pro_logo} /> */}
                                            <img src="pro_logo-1707935762510.png" />
                                        </div>
                                        <div>
                                            <p><strong>Office:</strong>603-B2, Floor 6, B Block,</p>
                                            <p><strong>PO Box:</strong>123916, Dubai UAE</p>
                                            <p><strong> Phone:</strong>+ 971 4 575 4857</p>
                                            <p><strong>Email:</strong>info@triacitsolutions.com</p>
                                            <p><strong>VAT TRN:</strong> 100430133700003</p>
                                        </div>
                                    </div>
                                </div>
                            </Grid>
                        </Grid>

                        <CorporateVoucherBody
                            salesOrderData={sales}
                            institution={institution}
                            authInfo={this.props.authInfo}
                        />

                        <Grid container style={{ padding: '0 1rem 0 1rem' }}>
                            <Grid item xs={6} sm={6} style={{}}>
                                <div className={"corparate-table-custom-column"}>   <div style={{ color: "#222" }}>
                                    AMOUNT IN WORDS :{" "}</div><div>
                                        {convertNumberToWords(sales.total_amount)}{" "}
                                    </div></div>

                                <table style={{ width: "100%", paddingRight: "20px" }}>
                                    <thead>
                                        {sales.paid_amount != 0 ? (
                                            <>
                                                <tr>
                                                    <th
                                                        colSpan={3}
                                                        style={{ width: "100%", textAlign: "left" }}
                                                    >
                                                        Paid - Received Into Accounts
                                                    </th>
                                                </tr>
                                                <tr>
                                                    <th style={{ width: "2%", textAlign: "left" }}>
                                                        NO.
                                                    </th>
                                                    <th style={{ width: "40%", textAlign: "left" }}>
                                                        {" "}
                                                        Cash/ Bank Account{" "}
                                                    </th>
                                                    <th style={{ width: "30%", textAlign: "left" }}>
                                                        {" "}
                                                        Description{" "}
                                                    </th>
                                                    <th style={{ width: "28%", textAlign: "left" }}>
                                                        {" "}
                                                        Amount{" "}
                                                    </th>
                                                </tr>
                                            </>
                                        ) : (
                                            ""
                                        )}
                                    </thead>
                                    <tbody>
                                        {sales.trans != undefined
                                            ? sales.trans.map((tran, sl) => (
                                                <>
                                                    <tr>
                                                        <td style={{ borderBottom: "1px solid #d1d0d0" }}>
                                                            {sl + parseFloat(1)}
                                                        </td>
                                                        <td style={{ borderBottom: "1px solid #d1d0d0" }}>
                                                            {tran.to_acc_name}
                                                        </td>
                                                        <td style={{ borderBottom: "1px solid #d1d0d0" }}>
                                                            {tran.acc_note}
                                                        </td>
                                                        <td style={{ borderBottom: "1px solid #d1d0d0" }}>
                                                            {format(
                                                                parseFloat(tran.tran_amount).toFixed(2)
                                                            )}
                                                        </td>
                                                    </tr>
                                                </>
                                            ))
                                            : ""}
                                    </tbody>
                                </table>



                                {sales.emi_month != 0 ? (
                                    <>
                                        <table style={{ width: "100%", paddingRight: "20px" }}>
                                            <thead>
                                                {sales.is_emi == "yes" ? (
                                                    <>
                                                        <tr>
                                                            <th
                                                                colSpan={3}
                                                                style={{ width: "100%", textAlign: "left" }}
                                                            >
                                                                {" "}
                                                                {sales.emi_month} Installments Payment
                                                            </th>
                                                        </tr>
                                                        <tr>
                                                            <th style={{ width: "15%", textAlign: "left" }}>
                                                                EMI No
                                                            </th>
                                                            <th style={{ width: "25%", textAlign: "left" }}>
                                                                {" "}
                                                                From Date{" "}
                                                            </th>
                                                            <th style={{ width: "30%", textAlign: "left" }}>
                                                                {" "}
                                                                Last Pay Date{" "}
                                                            </th>
                                                            <th style={{ width: "30%", textAlign: "left" }}>
                                                                {" "}
                                                                Amount{" "}
                                                            </th>
                                                        </tr>
                                                    </>
                                                ) : (
                                                    ""
                                                )}
                                            </thead>
                                            <tbody>
                                                {sales.emis != undefined
                                                    ? sales.emis.map((tran, sl) => (
                                                        <>
                                                            <tr>
                                                                <td
                                                                    style={{
                                                                        borderBottom: "1px solid #d1d0d0",
                                                                    }}
                                                                >
                                                                    {tran.emi_no}
                                                                </td>
                                                                <td
                                                                    style={{
                                                                        borderBottom: "1px solid #d1d0d0",
                                                                    }}
                                                                >
                                                                    {moment(tran.from_date).format(dateFormat)}
                                                                </td>
                                                                <td
                                                                    style={{
                                                                        borderBottom: "1px solid #d1d0d0",
                                                                    }}
                                                                >
                                                                    {moment(tran.last_date).format(dateFormat)}
                                                                </td>
                                                                <td
                                                                    style={{
                                                                        borderBottom: "1px solid #d1d0d0",
                                                                    }}
                                                                >
                                                                    {format(parseFloat(tran.amount).toFixed(2))}
                                                                </td>
                                                            </tr>
                                                        </>
                                                    ))
                                                    : ""}
                                            </tbody>
                                        </table>
                                    </>
                                ) : (
                                    ""
                                )}
                            </Grid>
                            <Grid xs={6} sm={6} >
                                <table style={{ width: "100%" }} className={"corparate-head-table"}>

                                    <tr>
                                        <td style={{ color: "#222", fontWeight: "normal", textAlign: 'left' }}>
                                            SUBTOTAL
                                        </td>
                                        <td
                                            style={{
                                                textAlign: "right",
                                                color: "#222",
                                                fontWeight: "normal",
                                            }}
                                        >
                                            {this.props.authInfo.currency} {" "}
                                            {format(parseFloat(sales.sub_total).toFixed(2))}{" "}
                                        </td>
                                    </tr>
                                    {sales.is_cal_type == "on_total" ? (
                                        <>
                                            <tr>
                                                <td style={{ color: "#222", fontWeight: "normal", textAlign: 'left' }}>
                                                    VAT
                                                </td>
                                                <td
                                                    style={{
                                                        textAlign: "right",
                                                        color: "#222",
                                                        fontWeight: "normal",
                                                    }}
                                                >
                                                    {this.props.authInfo.currency} {" "}
                                                    {format(parseFloat(sales.total_tax).toFixed(2))}{" "}
                                                </td>
                                            </tr>

                                        </>
                                    ) : (
                                        ""
                                    )}
                                    <tr>
                                        <td style={{ color: "#222", fontWeight: "bold", textAlign: 'left' }}>
                                            TOTAL
                                        </td>
                                        <td
                                            style={{
                                                textAlign: "right",
                                                color: "#222",
                                                fontWeight: "bold",
                                            }}
                                        >
                                            {this.props.authInfo.currency} {" "}
                                            {format(parseFloat(sales.total_amount).toFixed(2))}{" "}
                                        </td>
                                    </tr>


                                    {/* <tr>
                                        <td style={{ color: "#222", fontWeight: "bold", textAlign: 'left' }}>
                                            Paid : {this.props.authInfo.currency}
                                        </td>
                                        <td
                                            style={{
                                                textAlign: "right",
                                                color: "#222",
                                                fontWeight: "bold",
                                            }}
                                        >
                                            {this.props.authInfo.currency} {" "}
                                            {format(parseFloat(sales.paid_total).toFixed(2))}{" "}
                                        </td>
                                    </tr>

                                    <tr>
                                        <td style={{ color: "#222", fontWeight: "bold", textAlign: 'left' }}>
                                            Due : {this.props.authInfo.currency}
                                        </td>
                                        <td
                                            style={{
                                                textAlign: "right",
                                                color: "#222",
                                                fontWeight: "bold",
                                            }}
                                        >
                                            {this.props.authInfo.currency}{" "}
                                            {format(parseFloat(sales.due_total).toFixed(2))}{" "}
                                        </td>
                                    </tr> */}
                                </table>

                                {/*  */}
                            </Grid>

                            <Grid item xs={12} sm={12}>
                                <div style={{ display: 'flex' }}>

                                    <div style={{ width: '50%' }}>
                                        <p><strong>Bank Details</strong></p>
                                        <p>Bank Name: RAK Bank</p>
                                        <p>Account Name: TRIAC SOLUTIONS IT CONSULTANCY LLC</p>
                                        <p>Current A/C No: 0372878632</p>
                                        <p>IBAN: AE949846923846329</p>
                                        <p>Swift Code : NRAKAKAEAK</p>
                                    </div>
                                    <div style={{ width: '50%' }}><p>For : Triac Solutions IT Consultancy </p></div>
                                </div>
                            </Grid>
                        </Grid>
                    </>
                ) : (
                    ""
                )
                }
            </div>
        );
    }
}
