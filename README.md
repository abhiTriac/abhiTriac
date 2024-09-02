let [trade_licence_expiry, trade_licence_expiry_set] = useState(""); 
 const handleTradeLicenceExpiryChange = (date) => {
    if (date) {
      trade_licence_expiry_set(dayjs(date.$d));
    }
  };   
 <DatePicker
              onChange={handleTradeLicenceExpiryChange}
              format={dateMonthFormat}
              style={{ width: "100%" }}
              value={trade_licence_expiry ? trade_licence_expiry: ""}
            />

            <div className="company-body"><div>Trade Licence Expiry</div><div>{trade_licence_expiry ? dayjs(trade_licence_expiry) : ""}</div></div>
