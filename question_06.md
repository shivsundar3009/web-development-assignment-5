Promises are objects in JavaScript that represent the eventual completion (or failure) of an asynchronous operation and allow you to handle the result asynchronously. They provide a more structured and readable way to handle asynchronous code compared to callbacks.

Promises have three states:

1. Pending: The initial state when the Promise is created, and the asynchronous operation is still in progress.

2. Fulfilled: The state when the asynchronous operation is successfully completed, and the Promise is resolved with a value.

3. Rejected: The state when the asynchronous operation encounters an error or failure, and the Promise is rejected with a reason (an error object).

Here are three commonly used methods of Promises:

1. `then()`: The `then()` method is used to handle the fulfillment of a Promise. It takes two optional callback functions as arguments: `onFulfilled` and `onRejected`. The `onFulfilled` function is called when the Promise is fulfilled, and it receives the resolved value as an argument. The `onRejected` function is called when the Promise is rejected, and it receives the rejection reason as an argument.

Example:

```
fetchData()
  .then(function (result) {
    console.log(result); // Handle the fulfilled value
  })
  .catch(function (error) {
    console.log(error); // Handle the rejection reason
  });
```

2. `catch()`: The `catch()` method is used to handle the rejection of a Promise. It is equivalent to calling `.then(undefined, onRejected)`, allowing you to catch and handle errors that occurred during the Promise chain.

Example:

```
fetchData()
  .then(function (result) {
    console.log(result);
  })
  .catch(function (error) {
    console.log(error); // Handle the rejection reason
  });
```

3. `finally()`: The `finally()` method is used to specify a callback function that will be executed regardless of whether the Promise is fulfilled or rejected. It is commonly used to perform cleanup operations or finalize tasks that need to be done after the Promise is settled.

Example:

```
fetchData()
  .then(function (result) {
    console.log(result);
  })
  .catch(function (error) {
    console.log(error);
  })
  .finally(function () {
    console.log('Cleanup or final tasks');
  });
```

These methods allow you to handle the results of Promises and chain multiple asynchronous operations together in a more readable and maintainable way. They provide better error handling, reduce callback nesting, and improve code structure.