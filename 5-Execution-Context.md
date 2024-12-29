# JavaScript Execution Con

## 05-execution-con/

### Understanding Execution Con, Call Stack, and Event Loop

In JavaScript, the execution con is the environment in which the code is evaluated and executed. It contains information about the variables, functions, and objects that are accessible at any given point in time.

#### Types of Execution Cons

1. **Global Execution Con:** The default con where all JavaScript code runs initially.
2. **Function Execution Con:** Created whenever a function is invoked.
3. **Eval Execution Con:** Created by the `eval()` function (rarely used).

#### Call Stack

The call stack is a data structure that keeps track of function calls in a last-in-first-out (LIFO) manner.

```js
function first() {
  second();
  console.log("First function");
}
function second() {
  console.log("Second function");
}
first();
// Output:
// Second function
// First function
```

#### Event Loop

The event loop allows JavaScript to perform non-blocking operations by using callbacks, promises, and async functions.

```js
console.log("Start");
setTimeout(() => {
  console.log("Timeout");
}, 0);
console.log("End");
// Output:
// Start
// End
// Timeout
```

### Hoisting in JavaScript

Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their containing scope during the compilation phase.

#### Variable Hoisting

Variables declared with `var` are hoisted but initialized with `undefined`.

```js
console.log(x); // Outputs: undefined
var x = 5;
console.log(x); // Outputs: 5

Variables declared with `let` and `const` are also hoisted but remain uninitialized until their declaration is encountered.

console.log(y); // ReferenceError: Cannot access 'y' before initialization
let y = 10;
```

#### Function Hoisting

Function declarations are fully hoisted, allowing you to call them before they appear in the code.

```js
console.log(sayHello()); // Outputs: Hello!
function sayHello() {
  return "Hello!";
}
```

However, function expressions (including arrow functions) are not hoisted in the same way.

```js
console.log(sayGoodbye()); // TypeError: sayGoodbye is not a function
var sayGoodbye = function () {
  return "Goodbye!";
};
```

### Understanding `this`

The value of `this` in JavaScript depends on how a function is called. It can refer to different objects based on the con.

#### Global Con

In the global execution con (outside any function), `this` refers to the global object (`window` in browsers).

```js
console.log(this); // Outputs: Window object (in browsers)
```

#### Function Con

In a regular function, `this` refers to the global object unless it is called as a method of an object.

```js
function showThis() {
  console.log(this);
}
showThis(); // Outputs: Window object (in browsers)
const obj = {
  name: "Alice",
  showName: function () {
    console.log(this.name);
  },
};
obj.showName(); // Outputs: Alice
```

#### Arrow Functions

Arrow functions do not have their own `this`. They inherit `this` from the parent scope.

```js
const obj2 = {
  name: "Bob",
  showName: () => {
    console.log(this.name); // 'this' refers to the global object here
  },
};
obj2.showName(); // Outputs: undefined (if 'name' is not defined globally)
```

### Closures in Con of Execution

A closure is a function that retains access to its lexical scope even when the function is executed outside that scope. Closures are created every time a function is created.

#### Example of Closure

```js
function outerFunction() {
  let outerVar = "I am outside!";

  return function innerFunction() {
    console.log(outerVar); // Accesses outerVar from outerFunction's scope
  };
}
const closureFunc = outerFunction();
closureFunc(); // Outputs: I am outside!
```

#### Practical Use Case

Closures are often used to create private variables or functions.

```js
function createCounter() {
  let count = 0; // Private variable

  return {
    increment: function () {
      count++;
      return count;
    },
    decrement: function () {
      count--;
      return count;
    },
    getCount: function () {
      return count;
    },
  };
}
const counter = createCounter();
console.log(counter.increment()); // Outputs: 1
console.log(counter.increment()); // Outputs: 2
console.log(counter.getCount()); // Outputs: 2
console.log(counter.decrement()); // Outputs: 1
```

### Conclusion

This section covers essential concepts related to execution con in JavaScript, including understanding execution cons, the call stack, and event loop mechanics. It also delves into hoisting behavior, the nuances of the `this` keyword, and how closures work within execution cons. Mastering these concepts will significantly enhance your understanding of JavaScript's behavior and help you write more efficient code.
