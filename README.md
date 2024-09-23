    <AutoComplete
                    style={{ width: "100%" }}
                    options={[
                      {
                        value: "AddNew",
                        label: (<span className="addNewDropdown">
                          <img style={{ height: '0.8rem' }} src={createNew} />Add New</span>),
                        obj: null
                      },
                      ...locations.map((location) => ({
                        value: location.location_name,
                      }))]}
                    filterOption={(inputValue, option) => {
                      if (option.value === "AddNew") {
                        return true
                      }
                      if (typeof option.label === 'string') {
                        return option.label.toUpperCase().includes(inputValue.toUpperCase());
                      }
                      const textContent = option.label.props.children[1]; // Assuming text is the second child
                      return textContent.toUpperCase().includes(inputValue.toUpperCase());
                    }}
                    value={selectedLocation?.location_name}
                    onChange={locationChange}
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
