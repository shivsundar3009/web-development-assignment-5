To define an asynchronous function in JavaScript using `async/await`, you can use the `async` keyword before the function declaration. Here's the syntax:

```
async function functionName() {
  // Asynchronous code
}
```

Here's an example of an asynchronous function that uses `async/await` to handle asynchronous operations:

```
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    if (response.ok) {
      const data = await response.json();
      console.log(data);
    } else {
      throw new Error('Request failed with status ' + response.status);
    }
  } catch (error) {
    console.log(error);
  }
}
```

In this example, the `fetchData` function is defined as an asynchronous function using the `async` keyword. Inside the function, the `await` keyword is used to pause the execution and wait for the resolution of the `fetch` Promise. If the response is successful (status code 200-299), the response is converted to JSON using `await response.json()` and the retrieved data is logged. If an error occurs during the request, it is caught in the `catch` block.

By using `async/await`, you can write asynchronous code that resembles synchronous code in terms of readability and structure. The `await` keyword allows you to handle the results of Promises in a sequential and straightforward manner without relying on nested callbacks or chained `.then()` calls.