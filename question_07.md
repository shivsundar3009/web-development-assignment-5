The `async` and `await` keywords in JavaScript provide a more synchronous-like syntax for handling asynchronous operations. They are part of the ECMAScript 2017 (ES8) language specification.

Here's a breakdown of each keyword:

1. `async`: The `async` keyword is used to declare an asynchronous function. An async function always returns a Promise, allowing you to use the `await` keyword inside the function to pause the execution until a Promise is resolved or rejected. It allows you to write asynchronous code that looks and behaves more like synchronous code.

Example:

```
async function fetchData() {
  // Asynchronous operations
  const result = await someAsyncOperation();
  return result;
}
```

2. `await`: The `await` keyword is used to pause the execution within an async function until a Promise is fulfilled or rejected. It can only be used inside an async function. When encountering an `await` expression, the function execution is halted until the awaited Promise settles. If the Promise is fulfilled, the resolved value is returned. If the Promise is rejected, an error is thrown, which can be caught using `try...catch` blocks.

Example:

```
async function getData() {
  try {
    const result = await fetchData(); // Wait for the Promise to resolve
    console.log(result); // Handle the resolved value
  } catch (error) {
    console.log(error); // Handle any error that occurred
  }
}
```

Using `await` makes the code appear more linear and easier to read compared to callback-based or promise-chaining approaches. It allows you to write asynchronous code in a more sequential and intuitive manner, similar to traditional synchronous code.

It's important to note that the use of `await` is limited to within async functions. If you need to use `await`, ensure that the function containing it is declared with the `async` keyword.