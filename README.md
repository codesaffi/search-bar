FIRST IMPORT REACT AND USE STATE FROM REACT AND STYLE FILE


    import React, { useState } from 'react';
    import './index.css'



THEN CREATE STATE VARIABLE to store the value that is searched


    const [query, setQuery] = useState('');



THEN CREATE A FUNCTION WHICH WILL HANDLE CHANGES THAT WILL BE MADE IN SEARCH BAR AND STORE THE VALUE IN SET QUERY


    const handleInputChange = (e) => {
    setQuery(e.target.value);
  };


    
NOW CREATE YOUR DATA LIKE THIS


  const data = [
    { id: 1, name: 'Apple', description: 'A sweet red fruit', image: 'https://via.placeholder.com/150' },
    { id: 2, name: 'Banana', description: 'A long yellow fruit', image: 'https://via.placeholder.com/150' },
    { id: 3, name: 'Orange', description: 'A round orange fruit', image: 'https://via.placeholder.com/150' },
    { id: 4, name: 'Pineapple', description: 'A tropical fruit with spiky skin', image: 'https://via.placeholder.com/150' },
    { id: 5, name: 'Strawberry', description: 'A small red fruit with seeds on the outside', image: 'https://via.placeholder.com/150' },
  ];



NOW CREATE A FUNCTION THE FUNCTION WILL BE RUN ON  WHEN ANY DATA IS SEARCH



stores the filtered results based on the query.
  const filteredData = data.filter(item => 
    item.name.toLowerCase().includes(query.toLowerCase())
  );



The component renders a search bar with an input field.

The input field's value is controlled by the query state, and changes are handled by handleInputChange.

The filtered results are displayed with images, names, and descriptions.



  div className="App">
    div className="search-bar">
      input
        type="text"
        placeholder="Search..."
        value={query}
        onChange={handleInputChange}
      />
    /div>
    div className="results-list">
      {filteredData.map((result) => (
        div key={result.id} className="result-item">
          img src={result.image} alt={result.name} />
          div className="result-info">
            h3>{result.name}/h3>
            p>{result.description}/p>
          /div>
        /div>
      ))}
    /div>
  div>
    