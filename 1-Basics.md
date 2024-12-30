# JavaScript Basics

### Variables and Data Types

In JavaScript, variables are used to store data values. There are three ways to declare variables: `var`, `let`, and `const`.

#### Variable Declaration

```js
// Using var
var name = "Alice"; // Can be re-assigned
// Using let
let age = 30; // Can be re-assigned
// Using const
const birthYear = 1994; // Cannot be re-assigned
```

#### Data Types

JavaScript has several built-in data types:

- **String:** Represents .

  ```js
  let greeting = "Hello, World!";
  ```

- **Number:** Represents both integer and floating-point numbers.

  ```js
  let score = 95.5;
  ```

- **Boolean:** Represents true or false values.

  ```js
  let isStudent = true;
  ```

- **Object:** A collection of key-value pairs.

  ```js
  let person = {
    name: "Alice",
    age: 30,
    isStudent: false,
  };
  ```

- **Array:** A list-like object used to store multiple values.

  ```js
  let colors = ["red", "green", "blue"];
  ```

### operators

#### Operators in JavaScript

Operators are special symbols that perform operations on variables and values. Here are some common types:

#### Arithmetic Operators

```js
  let a = 10;
  let b = 5;
  let sum = a + b; // Addition: 15
  let difference = a - b; // Subtraction: 5
  let product = a \* b; // Multiplication: 50
  let quotient = a / b; // Division: 2
```

#### Comparison Operators

```js
let x = 10;
let y = 20;
console.log(x > y); // Greater than: false
console.log(x < y); // Less than: true
console.log(x === y); // Strict equality: false
```

#### Logical Operators

```js
let isAdult = true;
let hasID = false;
console.log(isAdult && hasID); // AND: false
console.log(isAdult || hasID); // OR: true
console.log(!isAdult); // NOT: false
```

### control-flow

#### Control Flow: if-else, Loops

Control flow statements allow you to dictate the order in which code executes based on conditions.

#### If-Else Statement

```js
let temperature = 30;
if (temperature > 25) {
  console.log("It's warm outside!");
} else {
  console.log("It's cold outside!");
}
```

#### Switch Statement

```js
let day = 3;
switch (day) {
  case 1:
    console.log("Monday");
    break;
  case 2:
    console.log("Tuesday");
    break;
  case 3:
    console.log("Wednesday");
    break;
  default:
    console.log("Another day");
}
```

#### Loops

##### For Loop

```js
for (let i = 0; i < 5; i++) {
  console.log(i); // Outputs: 0, 1, 2, 3, 4
}
```

##### While Loop

```js
let count = 0;
while (count < 5) {
  console.log(count);
  count++; // Outputs: 0, 1, 2, 3, 4
}
```

### functions

Functions are reusable blocks of code that perform a specific task. They can take parameters and return values.

#### Function Declaration

```js
function greet(name) {
  return "Hello, " + name + "!";
}
console.log(greet("Alice")); // Outputs: Hello, Alice!
```

#### Function Expression

```js

const square = function(x) {
return x \* x;
};
console.log(square(4)); // Outputs: 16

```

#### Arrow Functions

```js
const add = (a, b) => a + b;
console.log(add(5, 3)); // Outputs: 8
```

### Conclusion

This section covers the fundamental concepts of JavaScript basics. Understanding these concepts is crucial for building more complex applications and mastering the language.
