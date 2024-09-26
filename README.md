const formatDate = (date) => {
    const year = date.getFullYear();
    const month = String(date.getMonth() + 1).padStart(2, '0'); // Months are 0-indexed
    const day = String(date.getDate()).padStart(2, '0');
    const hours = '00'; // Set hours to 00
    const minutes = '00'; // Set minutes to 00
    const seconds = '00'; // Set seconds to 00

    return `${year}-${month}-${day} ${hours}:${minutes}:${seconds}`;
};
