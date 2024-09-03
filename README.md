 try {
      console.debug("---------TRAN_START-------");
      transaction = await Tran.sequelize.transaction();
      console.debug("---------LOG-------", transaction);

      if (payLoad.action == "create") {
        let exist = await Tran.countRows(
          `select item_name from tbl_items where item_name=?  and status= 'a' `,
          [payLoad.item_name],
          transaction
        );
        console.debug("exist: ", exist);

        if (exist > 0) {
          res.json({
            error: true,
            msg: `Item Name Already Exist.`,
          });
          return false;
        }
        delete payLoad.action;
        delete payLoad.item_id;
        delete payLoad.prev_photo;
        let [save, _] = await Tran.create(`tbl_items`, payLoad, transaction);

        await stockUpdate(
          "opening_qty",
          "plus",
          save,
          payLoad.opening_qty,
          req.user.user_branch_id,
          0,
          transaction
        );

        await itemCostUpdate(
          "plus",
          save,
          payLoad.opening_qty,
          payLoad.opening_rate,
          0,
          req.user.user_branch_id,
          0,
          transaction
        );

        if (_ && !save) {
          next(saveErr);
        } else {
          // end

          res.json({
            error: false,
            msg: `Item Name create successful.`,
          });
        }
      } else {
        let exist = await Tran.countRows(
          `select item_name from tbl_items where item_name=? and item_id != ? and status= 'a' `,
          [payLoad.item_name, payLoad.item_id],
          transaction
        );
        console.debug("exist_2: ", exist);

        if (exist > 0) {
          res.json({
            error: true,
            msg: `Item  Name Already Exist.`,
          });
          return false;
        }

        let item_id = payLoad.item_id;
        delete payLoad.action;
        delete payLoad.item_id;
        delete payLoad.branch_ids;
        delete payLoad.prev_photo;

        let beforeStock = await getStock(
          req,
          res,
          next,
          item_id,
          "",
          req.user.user_branch_id,
          0,
          transaction
        );
        beforeStock = beforeStock[0].current_qty;

        let prevItemData = await Tran.selectByCond(
          ` select * from tbl_items where item_id=? and status = 'a' `,
          [item_id],
          transaction
        );
        // previous Minus
        console.debug("prevItemData: ", prevItemData);

        await stockUpdate(
          "opening_qty",
          "minus",
          item_id,
          prevItemData[0].opening_qty,
          req.user.user_branch_id,
          0,
          transaction
        );
        await itemCostUpdate(
          "minus",
          item_id,
          prevItemData[0].opening_qty,
          prevItemData[0].opening_rate,
          beforeStock,
          req.user.user_branch_id,
          0,
          transaction
        );

        // Current  Plus
        beforeStock = await getStock(
          req,
          res,
          next,
          item_id,
          "",
          req.user.user_branch_id,
          0,
          transaction
        );
        beforeStock = beforeStock[0].current_qty;

        await stockUpdate(
          "opening_qty",
          "plus",
          item_id,
          payLoad.opening_qty,
          req.user.user_branch_id,
          0,
          transaction
        );
        await itemCostUpdate(
          "plus",
          item_id,
          payLoad.opening_qty,
          payLoad.opening_rate,
          beforeStock,
          req.user.user_branch_id,
          0,
          transaction
        );

        await Tran.update("tbl_items", payLoad, { item_id }, transaction);

        res.json({
          error: false,
          msg: `Item  update successful.`,
        });
      }
      console.debug("exist_3333: ");

      await transaction.commit();
    }
