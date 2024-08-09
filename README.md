 <Link
              to={{ pathname: `/settings/item-barcode/${props.rowData[0]}` }}
            >
            </Link>
            <img src={Barcode}
              style={{ cursor: "pointer", color: "#222", fontSize: "28px" }}
              onClick={() => { history(`/settings/item-barcode/${props.rowData[0]}`) }}
            />
            
