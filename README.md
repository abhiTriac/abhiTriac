  const getItems = async () => {
    await axios
      .post(
        `${BACKEND_API_URL}/api/get-items-by-search`,
        {
          query: item_name.trim(),
          search: true,
          partyType:
            selectedCustomer == null
              ? "sale_rate"
              : selectedCustomer.party_type,
        },
        { headers: { "auth-token": authInfo.token } }
      )
      .then((res) => {
        itemsSet(res.data);
      });
  };
 <AutoComplete
                  style={{ width: "100%" }}
                  options={items.map((item) => ({
                    value: item.display_text,
                    label: item.display_text,
                    obj: item,
                  }))}
                  onChange={handleChangeSelectItem}
                  value={selectedItem?.display_text}
                >
                  <Input
                    ref={item_ref}
                    onKeyDown={(e) => {
                      if (e.key === "Enter") {
                        if (items.length == 0 && item_name) {
                          plus_icon_show_set(true);
                        } else {
                          item_qty_ref.current.focus();
                        }
                      }
                    }}
                    onChange={handleOnChangeSelectItem}
                    // onChange={(e) => item_name_set(e.target.value)}
                    placeholder="Search Item"
                  />
                </AutoComplete>
                
