  <AutoComplete
                  style={{ width: "100%" }}
                  options={[
                    {
                      value: "AddNew",
                      label: <span style={{ display: "flex", justifyContent: "center", fontWeight: "bold", alignItems: "center", gap: "0.5rem" }}>
                        <img style={{ height: '0.8rem' }} src={createNew} />Add New</span>,
                      obj: null
                    },
                    ...items.map((item) => ({
                      value: item.display_text,
                      label: item.display_text,
                      obj: item,
                    })),
                  ]}
                  onChange={handleChangeSelectItem}
                  value={selectedItem?.display_text}
                  filterOption={(inputValue, option) =>
                    option.label.toUpperCase().indexOf(inputValue.toUpperCase()) !==
                    -1
                  }
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
                ught TypeError: option.label.toUpperCase is not a function
    at filterOption (sales_entry.js:1821:1)
