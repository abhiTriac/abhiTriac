router.post(`/api/save-item`, async (req, res, next) => {
  uploadSingleItem(req, res, async function (err) {
    console.debug("----------uploadSingleItem----------");
    let payLoad = req.body;

    if (err instanceof multer.MulterError) {
      res.json(err);
      // A Multer error occurred when uploading.
    } else if (err) {
      res.json(err);
      // An unknown error occurred when uploading.
    }
    console.debug("---------ERR_1-------");

    payLoad.photo =
      payLoad.photo != "" &&
        res.req &&
        res.req.file &&
        res.req.file.filename != undefined
        ? res.req.file.filename
        : "";
    if (payLoad.photo == "" && payLoad.action == "update") {
      delete payLoad.photo;
    } else {
    }

    if (
      payLoad.photo != "" &&
      payLoad.action == "update" &&
      payLoad.prev_photo != "" &&
      payLoad.prev_photo != "null" &&
      payLoad.prev_photo != null
    ) {
      fs.stat(`./uploads/${payLoad.prev_photo}`, function (err, stats) {
        console.log(stats); //here we got all information of file in stats variable

        if (err) {
          return console.error(err);
        }

        fs.unlink(`./uploads/${payLoad.prev_photo}`, function (err) {
          if (err) return console.log(err);
          console.log("file deleted successfully");
        });
      });
    }

    // End photo upload

    payLoad.create_by = req.user.user_id;
    payLoad.branch_ids = req.user.user_branch_id;

    let transaction;

    try {
      console.debug("---------TRAN_START-------", Tran);
      // console.debug("---------LOG-------", Tran.pool());
      let connection = await Tran.pool.getConnection();
      transaction = connection.beginTransaction();

      if (payLoad.action == "create") {
        let exist = await Tran.countRows(
          `select item_name from tbl_items where item_name=?  and status= 'a' `,
          [payLoad.item_name],
          connection
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
        let [save, _] = await Tran.create(`tbl_items`, payLoad, connection);

        await stockUpdate(
          "opening_qty",
          "plus",
          save,
          payLoad.opening_qty,
          req.user.user_branch_id,
          0,
          connection
        );

        await itemCostUpdate(
          "plus",
          save,
          payLoad.opening_qty,
          payLoad.opening_rate,
          0,
          req.user.user_branch_id,
          0,
          connection
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
          connection
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
          connection
        );
        beforeStock = beforeStock[0].current_qty;

        let prevItemData = await Tran.selectByCond(
          ` select * from tbl_items where item_id=? and status = 'a' `,
          [item_id],
          connection
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
          connection
        );
        await itemCostUpdate(
          "minus",
          item_id,
          prevItemData[0].opening_qty,
          prevItemData[0].opening_rate,
          beforeStock,
          req.user.user_branch_id,
          0,
          connection
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
          connection
        );
        beforeStock = beforeStock[0].current_qty;

        await stockUpdate(
          "opening_qty",
          "plus",
          item_id,
          payLoad.opening_qty,
          req.user.user_branch_id,
          0,
          connection
        );
        await itemCostUpdate(
          "plus",
          item_id,
          payLoad.opening_qty,
          payLoad.opening_rate,
          beforeStock,
          req.user.user_branch_id,
          0,
          connection
        );

        await Tran.update("tbl_items", payLoad, { item_id }, transaction);

        res.json({
          error: false,
          msg: `Item  update successful.`,
        });
      }
      console.debug("exist_3333: ");

      await connection.commit();
    } catch (err) {
      if (typeof connection != 'undefined') {
        try {
          await connection.rollback()
        } catch (error) {
          console.error(error)
        }
      }
      next(err);
    }
  });
});
