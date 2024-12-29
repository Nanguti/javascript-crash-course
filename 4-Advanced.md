# JavaScript Advanced Concepts

## 04-advanced/

### Higher-Order Functions and Functional Programming

Higher-order functions are functions that take other functions as arguments or return them as results. They are a key feature of functional programming.

#### Example of a Higher-Order Function

```js
function greet(name) {
return Hello, ${name}!;
}
function processUserInput(callback) {
const name = prompt("Please enter your name:");
console.log(callback(name));
}
processUserInput(greet);
```

#### Functional Programming Concepts

1. **Pure Functions:** Functions that do not have side effects and return the same output for the same input.

   ```js
   function add(a, b) {
     return a + b; // Pure function
   }
   ```

2. **Immutability:** Avoiding changes to existing data structures.

   ```js
   const originalArray = [1, 2, 3];
   const newArray = [...originalArray, 4]; // Creates a new array
   ```

3. **Function Composition:** Combining multiple functions to create a new function.

   ```js
   const double = x => x _ 2;
   const square = x => x _ x;
   const doubleThenSquare = x => square(double(x));
   console.log(doubleThenSquare(3)); // Outputs: 36
   ```

### Promises In-Depth and Async Handling

Promises are a way to handle asynchronous operations in JavaScript. They represent a value that may be available now, or in the future, or never.

#### Creating and Using Promises

```js
const fetchData = new Promise((resolve, reject) => {
  setTimeout(() => {
    const data = { id: 1, name: "Alice" };
    resolve(data); // Resolve the promise with data
    // reject(new Error("Failed to fetch data")); // Uncomment to see error handling
  }, 1000);
});
// Using Promises
fetchData
  .then((result) => {
    console.log(result); // Outputs: { id: 1, name: "Alice" }
  })
  .catch((error) => {
    console.error(error);
  });
```

#### Async/Await Syntax

Async/await is syntactic sugar built on top of promises, making asynchronous code easier to read and write.

```js
async function fetchDataAsync() {
  try {
    const data = await fetchData; // Wait for the promise to resolve
    console.log(data); // Outputs: { id: 1, name: "Alice" }
  } catch (error) {
    console.error(error);
  }
}
fetchDataAsync();
```

### ES6 Modules (Import/Export)

JavaScript ES6 introduced modules to help organize code into reusable pieces. You can export variables, functions, or classes from one module and import them into another.

#### Exporting Modules

```js
// math.js
export const PI = 3.14;
export function add(a, b) {
  return a + b;
}
```

#### Importing Modules

```js
// main.js
import { PI, add } from "./math.js";
console.log(PI); // Outputs: 3.14
console.log(add(2, 3)); // Outputs: 5
```

#### Default Exports

You can also export a single default value from a module.

```js
// greeting.js
export default function greet(name) {
return Hello, ${name}!;
}
// main.js
import greet from './greeting.js';
console.log(greet("Alice")); // Outputs: Hello, Alice!
```

### Design Patterns in JavaScript

Design patterns are standard solutions to common problems in software design. Here are some commonly used patterns in JavaScript:

#### Module Pattern

The module pattern helps encapsulate private variables and expose public methods.

```js
const Counter = (function () {
  let count = 0; // Private variable

  return {
    increment: function () {
      count++;
      console.log(count);
    },
    decrement: function () {
      count--;
      console.log(count);
    },
  };
})();
Counter.increment(); // Outputs: 1
Counter.increment(); // Outputs: 2
Counter.decrement(); // Outputs: 1
```

#### Singleton Pattern

The singleton pattern restricts instantiation of a class to one object.

```js
const Singleton = (function () {
  let instance;

  function createInstance() {
    return { name: "I am the instance" };
  }

  return {
    getInstance: function () {
      if (!instance) {
        instance = createInstance();
      }
      return instance;
    },
  };
})();
const instance1 = Singleton.getInstance();
const instance2 = Singleton.getInstance();
console.log(instance1 === instance2); // Outputs: true
```

### Garbage Collection and Memory Management

JavaScript uses automatic garbage collection to manage memory. The garbage collector frees up memory occupied by objects that are no longer needed.

#### How Garbage Collection Works

- **Mark-and-Sweep Algorithm:** The garbage collector marks objects that are reachable from root references (like global variables), then sweeps through memory to free unmarked objects.

#### Memory Leaks

Memory leaks occur when memory that is no longer needed is not released. Common causes include:

- Global variables that are not cleaned up.
- Forgotten timers or callbacks.
- Detached DOM elements.

#### Preventing Memory Leaks

- Use local variables instead of global ones.
- Clear intervals and timeouts when they are no longer needed.
- Remove event listeners when they are no longer necessary.

### Conclusion

This section covers advanced concepts in JavaScript, including higher-order functions and functional programming principles, in-depth handling of promises and async operations, ES6 module syntax for organizing code, common design patterns for structuring applications, and an understanding of memory management and garbage collection. Mastering these topics will greatly enhance your ability to write efficient and maintainable JavaScript code.
