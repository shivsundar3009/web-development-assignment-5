In JavaScript, you can handle asynchronous code using various techniques and features. Here are a few commonly used approaches:

1. Callbacks: Callback functions are a traditional way to handle asynchronous operations in JavaScript. You can pass a function as a parameter to an asynchronous function, and that function gets called once the asynchronous operation is complete. However, this can lead to callback hell when dealing with multiple asynchronous operations.

Example:

```
function fetchData(callback) {
  setTimeout(function () {
    const data = 'Async data';
    callback(data);
  }, 2000);
}

fetchData(function (result) {
  console.log(result);
});
```

2. Promises: Promises provide a more structured way to handle asynchronous code. A promise represents the eventual completion or failure of an asynchronous operation and allows you to chain multiple asynchronous operations together using methods like `.then()` and `.catch()`.

Example:

```
function fetchData() {
  return new Promise(function (resolve, reject) {
    setTimeout(function () {
      const data = 'Async data';
      resolve(data);
    }, 2000);
  });
}

fetchData()
  .then(function (result) {
    console.log(result);
  })
  .catch(function (error) {
    console.log(error);
  });
```

3. Async/await: The async/await syntax is built on top of promises and provides a more synchronous-like way to write asynchronous code. The `async` keyword is used to define an asynchronous function, and the `await` keyword is used to pause the execution of the function until a promise is resolved.

Example:

```
function fetchData() {
  return new Promise(function (resolve, reject) {
    setTimeout(function () {
      const data = 'Async data';
      resolve(data);
    }, 2000);
  });
}

async function getData() {
  try {
    const result = await fetchData();
    console.log(result);
  } catch (error) {
    console.log(error);
  }
}

getData();
```

These are some of the commonly used methods to handle asynchronous code in JavaScript. Each approach has its advantages and use cases, so choose the one that best suits your specific requirements and coding style.