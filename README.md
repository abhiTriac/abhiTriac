 <Link
              to={{ pathname: `/settings/item-barcode/${props.rowData[0]}` }}
            >
            </Link>
            <img src={Barcode}
              style={{ cursor: "pointer", color: "#222", fontSize: "28px" }}
              onClick={() => { history(`/settings/item-barcode/${props.rowData[0]}`) }}
            />
            


import React from 'react';
import { useNavigate } from 'react-router-dom';
import Barcode from './path/to/your/BarcodeImage'; // Update with the correct path

const YourComponent = (props) => {
  const navigate = useNavigate();

  const handleImageClick = () => {
    // Construct the dynamic path using props.rowData[0]
    const dynamicPath = `/settings/item-barcode/${props.rowData[0]}`;
    // Navigate to the dynamic path
    navigate(dynamicPath);
  };

  return (
    <div>
      {/* Image with onClick handler */}
      <img
        src={Barcode}
        alt="Barcode"
        style={{ cursor: 'pointer', color: '#222', fontSize: '28px' }}
        onClick={handleImageClick} // Trigger navigation on click
      />
    </div>
  );
};

export default YourComponent;
