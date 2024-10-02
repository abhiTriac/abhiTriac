
  useEffect(() => {
    const updateDateTime = () => {
      const date = new Date();

      const day = date.getDate().toString().padStart(2, "0");
      const month = (date.getMonth() + 1).toString().padStart(2, "0"); // Months are zero-indexed
      const year = date.getFullYear();

      let hours = date.getHours();
      const minutes = date.getMinutes().toString().padStart(2, "0");
      const ampm = hours >= 12 ? "PM" : "AM";
      hours = hours % 12;
      hours = hours ? hours : 12;
      const strTime = `${hours.toString().padStart(2, "0")}:${minutes} ${ampm}`;

      const formattedDateTime = `${day}-${month}-${year} ${strTime}`;
      setDateTime(formattedDateTime);
    };

    const interval = setInterval(updateDateTime, 1000);

    return () => clearInterval(interval);
  }, []);
