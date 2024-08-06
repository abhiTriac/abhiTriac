<AutoComplete
                    style={{ width: "100%" }}
                    options={locations.map((location) => ({
                      value: location.location_name,
                    }))}
                    filterOption={(inputValue, option) =>
                      option.value
                        .toUpperCase()
                        .indexOf(inputValue.toUpperCase()) !== -1
                    }
                    value={selectedLocation ? selectedLocation.location_name : ""}
                    onChange={(value) => {
                      const selectedObj = locations.find(
                        (location) => location.location_name === value
                      );
                      selectedLocationSet(selectedObj);
                    }}
                  >
                    <Input
                      ref={location_ref}
                      onKeyDown={(event) => {
                        if (event.key === "Enter") {
                          email_ref.current.focus();
                        }
                      }}
                      placeholder="Location/ Area"
                    />
                  </AutoComplete>
