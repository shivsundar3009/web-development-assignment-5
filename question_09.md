`fetch` is a built-in function in JavaScript that is used to make HTTP requests and retrieve resources from a network. It provides a modern alternative to older methods like XMLHttpRequest (XHR) for making AJAX requests.

The `fetch` function returns a Promise that resolves to the `Response` object representing the response to the request. The `Response` object contains information about the response, such as the status code, headers, and the response body.

Here's a basic example of using `fetch` to make a GET request and retrieve data:

```
fetch('https://api.example.com/data')
  .then(function(response) {
    // Check the response status
    if (response.ok) {
      // Convert the response to JSON format
      return response.json();
    } else {
      throw new Error('Request failed with status ' + response.status);
    }
  })
  .then(function(data) {
    // Work with the retrieved data
    console.log(data);
  })
  .catch(function(error) {
    // Handle any errors that occurred during the request
    console.log(error);
  });
```

In this example, `fetch` is called with the URL of the resource to retrieve. The resulting Promise is then handled using `.then()` and `.catch()` methods. Inside the first `.then()` block, the response is checked for a successful status code (200-299). If successful, the response is converted to JSON using the `.json()` method. The resulting Promise is then passed to the next `.then()` block, where you can work with the retrieved data. If the response has an error status code, an error is thrown and caught in the `.catch()` block for error handling.

`fetch` can be used to make different types of requests (GET, POST, PUT, DELETE, etc.) by providing additional options in the second parameter. These options include the request method, headers, body, and more.

Note that `fetch` operates by default in a "cors" mode, meaning it follows cross-origin resource sharing rules. If you need to make requests to a different origin, ensure that the server supports cross-origin requests or includes the necessary CORS headers.

`fetch` is widely supported in modern browsers and is commonly used for making asynchronous requests and interacting with APIs.