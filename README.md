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
                
