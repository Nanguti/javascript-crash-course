# JavaScript Core Concepts

### Working with Objects and Arrays

In JavaScript, objects and arrays are fundamental data structures.

#### Objects

Objects are collections of key-value pairs.

```js
// Creating an object
let person = {
  name: "Alice",
  age: 30,
  isStudent: false,
  greet: function () {
    console.log("Hello, my name is " + this.name);
  },
};
// Accessing object properties
console.log(person.name); // Outputs: Alice
console.log(person["age"]); // Outputs: 30
// Calling a method
person.greet(); // Outputs: Hello, my name is Alice
```

##### Arrays

Arrays are ordered lists of values.

```js
// Creating an array
let colors = ["red", "green", "blue"];
// Accessing array elements
console.log(colors); // Outputs: red
// Adding an element to the array
colors.push("yellow");
console.log(colors); // Outputs: ["red", "green", "blue", "yellow"]
```

### scope-and-closures

Scope determines the accessibility of variables in JavaScript.

#### Scope Types

1. **Global Scope:** Variables declared outside any function.
2. **Function Scope:** Variables declared within a function.
3. **Block Scope:** Variables declared with `let` or `const` within a block (e.g., if statements, loops).

```js
let globalVar = "I am global";
function myFunction() {
  let functionVar = "I am local";
  console.log(globalVar); // Accessible
}
myFunction();
console.log(functionVar); // ReferenceError: functionVar is not defined
```

#### Closures

A closure is a function that retains access to its lexical scope, even when the function is executed outside that scope.

```js
function outerFunction() {
  let outerVar = "I am from outer function";

  return function innerFunction() {
    console.log(outerVar); // Accesses outerVar from outerFunction's scope
  };
}
const innerFunc = outerFunction();
innerFunc(); // Outputs: I am from outer function
```

### dom-manipulation

The Document Object Model (DOM) represents the structure of a document (like HTML) as a tree of objects. JavaScript can manipulate the DOM to change the content and structure of web pages.

#### Selecting Elements

```js
// Select an element by ID
let heading = document.getElementById("myHeading");
// Select elements by class name
let items = document.getElementsByClassName("item");
// Select elements using querySelector
let firstItem = document.querySelector(".item");
```

#### Modifying Elements

```js
// Change content
heading.Content = "New Heading";
// Change styles
heading.style.color = "blue";
```

#### Adding Elements

```js
// Create a new element
let newElement = document.createElement("p");
newElement.Content = "This is a new paragraph.";
// Append the new element to the body
document.body.appendChild(newElement);
```

### Handling Events and Event Listeners

Events are actions that occur in the browser, such as clicks, key presses, or mouse movements. You can respond to these events using event listeners.

#### Adding Event Listeners

```js
// Select an element
let button = document.querySelector("button");
// Add a click event listener
button.addEventListener("click", function () {
  alert("Button was clicked!");
});
```

#### Removing Event Listeners

```js
function handleClick() {
  alert("Button was clicked!");
}
button.addEventListener("click", handleClick);
// Later in your code...
button.removeEventListener("click", handleClick);
```

### array-methods

JavaScript provides several built-in methods for manipulating arrays.

#### Common Array Methods:

- **forEach:** Executes a provided function once for each array element.

```js
let numbers = [1, 2, 3];
numbers.forEach(function (num) {
  console.log(num); // Outputs: 1, 2, 3
});
```

- **map:** Creates a new array populated with the results of calling a provided function on every element in the calling array.

```js
  let doubled = numbers.map(function(num) {
  return num \* 2;
  });
  console.log(doubled); // Outputs: [2, 4, 6]
```

- **filter:** Creates a new array with all elements that pass the test implemented by the provided function.

```js
let evenNumbers = numbers.filter(function (num) {
  return num % 2 === 0;
});
console.log(evenNumbers); // Outputs: []
```

- **reduce:** Executes a reducer function on each element of the array, resulting in a single output value.

```js
let sum = numbers.reduce(function (total, num) {
  return total + num;
}, 0);
console.log(sum); // Outputs: 6
```

### Conclusion

This section covers essential core concepts in JavaScript, including working with objects and arrays, understanding scope and closures, manipulating the DOM, handling events, and utilizing array methods. Mastering these topics will significantly enhance your ability to write effective JavaScript code.
