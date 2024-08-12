 const addPay = () => {
    if (selectedCustomer == null) {
      swal({
        title: `Select Customer`,
        icon: "warning",
      });
      return false;
    } else if (selectedFromAcc == null) {
      swal({
        title: `Select From Account`,
        icon: "warning",
      });
      return false;
    } else if (tran_amount == "" || tran_amount == 0) {
      swal({
        title: `Transaction Amount is Required.`,
        icon: "warning",
      });
      return false;
    } else {
      let pay = {
        to_acc_id: selectedFromAcc.acc_id,
        to_acc_name: selectedFromAcc.acc_name,
        tran_amount: tran_amount == "" ? 0 : tran_amount,
      };
      payCartSet([...payCart, pay]);
      selectedFromAccSet(null);
      tran_amount_set("");
    }
  };
