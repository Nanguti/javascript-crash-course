# JavaScript Intermediate Concepts

## 03-intermediate/

### asynchronous-javascript.md

**Asynchronous JavaScript: Callbacks, Promises, and async/await**

JavaScript is single-threaded, meaning it can only execute one operation at a time. Asynchronous programming allows you to perform tasks without blocking the execution of code.

#### Callbacks

A callback is a function passed as an argument to another function, which is executed after some operation is completed.

function fetchData(callback) {
setTimeout(() => {
const data = { id: 1, name: "Alice" };
callback(data);
}, 1000);
}
fetchData(function(result) {
console.log(result); // Outputs: { id: 1, name: "Alice" }
});

#### Promises

A Promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value.

let fetchDataPromise = new Promise((resolve, reject) => {
setTimeout(() => {
const data = { id: 1, name: "Alice" };
resolve(data); // Resolve the promise with data
}, 1000);
});
fetchDataPromise
.then(result => {
console.log(result); // Outputs: { id: 1, name: "Alice" }
})
.catch(error => {
console.error(error);
});

#### async/await

`async` functions return a promise, and `await` is used to wait for that promise to resolve.

async function fetchDataAsync() {
const data = await fetchDataPromise; // Wait for the promise to resolve
console.log(data); // Outputs: { id: 1, name: "Alice" }
}
fetchDataAsync();

### error-handling.md

**Error Handling in JavaScript**

Effective error handling is crucial for building robust applications. JavaScript provides `try`, `catch`, and `finally` statements for error handling.

#### Try-Catch Example:

try {
let result = riskyFunction(); // Function that may throw an error
} catch (error) {
console.error("An error occurred:", error.message);
} finally {
console.log("This will always run.");
}

#### Throwing Custom Errors:

You can throw custom errors using the `throw` statement.

function validateAge(age) {
if (age < 18) {
throw new Error("You must be at least 18 years old.");
}
return true;
}
try {
validateAge(16);
} catch (error) {
console.error(error.message); // Outputs: You must be at least 18 years old.
}

### oop.md

**Object-Oriented Programming Concepts**

JavaScript supports Object-Oriented Programming (OOP) principles such as encapsulation, inheritance, and polymorphism through classes.

#### Classes and Instances:

class Person {
constructor(name, age) {
this.name = name;
this.age = age;
}

greet() {
console.log(`Hello, my name is ${this.name}.`);
}
}
const alice = new Person("Alice", 30);
alice.greet(); // Outputs: Hello, my name is Alice.

#### Inheritance:

You can create subclasses that inherit properties and methods from a parent class.

class Student extends Person {
constructor(name, age, major) {
super(name, age); // Call the parent class constructor
this.major = major;
}

study() {
console.log(`${this.name} is studying ${this.major}.`);
}
}
const bob = new Student("Bob", 22, "Computer Science");
bob.greet(); // Outputs: Hello, my name is Bob.
bob.study(); // Outputs: Bob is studying Computer Science.

### functions-in-depth.md

**Advanced Functions and Callbacks**

Functions in JavaScript are first-class citizens; they can be assigned to variables, passed as arguments, and returned from other functions.

#### Higher-Order Functions:

A higher-order function is a function that takes another function as an argument or returns a function as a result.

function higherOrderFunction(callback) {
callback();
}
higherOrderFunction(() => {
console.log("This is a callback function.");
}); // Outputs: This is a callback function.

#### Function Currying:

Currying is the process of transforming a function with multiple arguments into a sequence of functions each taking a single argument.

function multiply(a) {
return function(b) {
return a \* b;
};
}
const double = multiply(2);
console.log(double(5)); // Outputs: 10

#### Closures in Depth:

Closures allow functions to access variables from their outer scope even after the outer function has finished executing.

function makeCounter() {
let count = 0;

return function() {
count++;
return count;
};
}
const counter = makeCounter();
console.log(counter()); // Outputs: 1
console.log(counter()); // Outputs: 2

### Conclusion

This section covers intermediate concepts in JavaScript, including asynchronous programming with callbacks and promises, effective error handling techniques, object-oriented programming principles like classes and inheritance, and advanced functions such as higher-order functions and currying. Mastering these concepts will enhance your ability to write more complex and maintainable JavaScript code.
