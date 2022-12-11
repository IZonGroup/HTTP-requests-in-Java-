// HTTP-requests-in-Java

// To make an HTTP request in JavaScript, you can use the XMLHttpRequest object or the more modern fetch() function. Here's an example of how to use XMLHttpRequest to make a GET request to retrieve data from a server:

// Create a new XMLHttpRequest object
var xhr = new XMLHttpRequest();

// Open a new connection to the server
x3hr.open('GET', 'https://www.example.com/api/data', true);

// Set the request headers
xhr.setRequestHeader('Content-Type', 'application/json');

// Send the request
xhr.send();

// Handle the response
xhr.onload = function() {
  if (xhr.status == 200) {
    // If the request was successful, parse the response data as JSON
    var data = JSON.parse(xhr.responseText);

    // Do something with the data
    console.log(data);
  } else {
    // If the request was not successful, log the error message
    console.error('An error occurred: ' + xhr.statusText);
  }
};

// Here is how to do the same thing wirth 'fetch' 
// fetch() is not supported in all browsers, so you may need to include a polyfill if you want to use it in older browsers.

// Make the request
fetch('https://www.example.com/api/data')
  .then(function(response) {
    // Parse the response as JSON
    return response.json();
  })
  .then(function(data) {
    // Do something with the data
    console.log(data);
  })
  .catch(function(error) {
    // If there was an error, log it
    console.error(error);
  });

