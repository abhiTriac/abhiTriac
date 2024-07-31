import React from 'react';

const EmployeeExpiry = ({ employee }) => {
  // Extract the relevant properties
  const {
    days_until_insurance_expiry,
    days_until_labour_contract_expiry,
    days_until_national_id_expiry,
    days_until_visa_expiry,
    insurance_expiry,
    labour_contract_expiry,
    national_id_expiry,
    visa_expiry,
    employee_name
  } = employee;

  // Create an array of the expiry values and their corresponding dates
  const expiryValues = [
    { days: days_until_insurance_expiry, date: insurance_expiry },
    { days: days_until_labour_contract_expiry, date: labour_contract_expiry },
    { days: days_until_national_id_expiry, date: national_id_expiry },
    { days: days_until_visa_expiry, date: visa_expiry }
  ];

  // Filter out null values and find the minimum value
  const nonNullValues = expiryValues.filter(value => value.days !== null);
  const minExpiryValue = Math.min(...nonNullValues.map(value => value.days));

  // Find the corresponding expiry date for the minimum expiry value
  const minExpiryDate = nonNullValues.find(value => value.days === minExpiryValue)?.date;

  return (
    <div>
      <h2>Employee: {employee_name}</h2>
      {nonNullValues.length > 0 ? (
        <div>
          <p>Days until nearest expiry: {minExpiryValue}</p>
          <p>Nearest expiry date: {new Date(minExpiryDate).toLocaleDateString()}</p>
          <p>All non-null expiry values: {nonNullValues.map(value => `${value.days} (${new Date(value.date).toLocaleDateString()})`).join(', ')}</p>
        </div>
      ) : (
        <p>No expiry dates available</p>
      )}
    </div>
  );
};

// Usage example:
const App = () => {
  const employees = [{
    branch_id: 1,
    days_until_insurance_expiry: 14,
    days_until_labour_contract_expiry: null,
    days_until_national_id_expiry: null,
    days_until_visa_expiry: null,
    employee_name: "Jon Snow",
    insurance_expiry: "2024-08-13T18:30:00.000Z",
    labour_contract_expiry: "2024-07-03T18:30:00.000Z",
    national_id_expiry: "2024-07-30T11:30:06.242Z",
    visa_expiry: "2024-07-30T11:30:06.242Z"
  }];

  return (
    <div>
      <h1>Employee Expiry Information</h1>
      {employees.map((employee, index) => (
        <EmployeeExpiry key={index} employee={employee} />
      ))}
    </div>
  );
};

export default App;
