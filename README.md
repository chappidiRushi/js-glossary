# JavaScript Glossary

This glossary provides brief explanations of common terms and concepts related to JavaScript.

## A

### Array

A data structure that stores a collection of elements, typically of the same type, accessible by an index.

### Arrow Function

A concise way to write anonymous function expressions in JavaScript using the `=>` syntax.

### Async/Await

A pair of keywords used to work with asynchronous code in a more synchronous-like manner, introduced in ES8 (ECMAScript 2017).

### API (Application Programming Interface)

A set of rules and protocols that allows different software applications to communicate with each other.

### AJAX (Asynchronous JavaScript and XML)

A technique for creating interactive web applications by exchanging data with a server asynchronously without reloading the page.

### Argument

Actual values passed to the function when it is invoked.

### Assignment Operator (`=`)

An operator used to assign a value to a variable.

### Array Method

A function that operates on arrays to perform tasks like adding, removing, or transforming elements.

### Arithmetic Operator

Operators used to perform arithmetic operations, such as addition (+), subtraction (-), multiplication (*), division (/), and modulus (%).

### Access Modifiers

Keywords used to specify the accessibility of class members in object-oriented programming languages.

### Abstraction

The process of hiding the implementation details and showing only the essential features of an object or function.

### Algorithm

A set of step-by-step instructions for solving a problem or completing a task, often expressed as pseudocode or in a programming language.

### Authentication

The process of verifying the identity of a user or system, often used in web applications to restrict access to certain resources.

### Animation

The process of creating the illusion of motion by displaying a series of images or frames in rapid succession.

### API Endpoint

A specific URL where an API can be accessed and interacted with.

### Array Index

The position of an element in an array, starting from zero for the first element.

### AJV (Another JSON Schema Validator)

A popular library for validating JSON data against JSON Schema definitions.

### Abstract Class

A class that cannot be instantiated and is typically used as a base class for other classes to inherit from.

## B

### Boolean

A data type that can have one of two values: true or false.

### Break

A keyword used to exit a loop prematurely, skipping the remaining iterations.

### Bitwise

Refers to operators that perform bitwise operations on binary representations of numbers.

### Block

A group of statements enclosed in curly braces { }, often used to define scope in JavaScript.

### Block Scope

The scope of variables defined within a block, such as within a function or loop.

### Break Statement

A statement used to exit a loop or switch statement prematurely.

### Browser Object Model (BOM)

A set of objects provided by web browsers, which expose the browser functionality to JavaScript.

### Bind

A method used to create a new function that, when called, has a specified 'this' value and optional initial arguments.

### Buffer

A temporary storage location used to hold data during input and output operations.

### Babel

A JavaScript compiler that transforms modern JavaScript code into backward-compatible versions for older browsers.

### Bubble Sort

A sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order.



## C

### Closure
A closure is a combination of a function and the lexical environment within which that function was declared. This allows the function to retain access to variables from its containing scope even after the scope has closed.

### Callback Function
A callback function, often referred to simply as a callback, is a function that is passed as an argument to another function and is executed after a particular event or operation has occurred.

## D

### Destructuring
A syntax for unpacking values from arrays or properties from objects into distinct variables.

### Example:
```js
// Array Destructuring
const [a, b] = [1, 2];
console.log(a); // Outputs: 1
console.log(b); // Outputs: 2

// Object Destructuring
const { x, y } = { x: 10, y: 20 };
console.log(x); // Outputs: 10
console.log(y); // Outputs: 20
```

### DOM
The Document Object Model (DOM) is a programming interface for web documents. It represents the structure of HTML and XML documents as a tree-like structure, allowing programs to dynamically access and manipulate the content, structure, and style of web documents.

## E

### Event
An event is a signal that indicates that a specific action has occurred. In JavaScript, events can be triggered by user interactions (such as clicking a button or typing on a keyboard) or by other parts of the program (such as loading a web page or receiving data from a server).

### Event Listener
An event listener is a function that listens for a specific event to occur and executes a specified piece of code (the event handler) in response to that event.

### Event delegation

Event delegation is a technique in JavaScript where you attach an event listener to a parent element instead of attaching it to the individual child elements. When an event occurs on a child element, it "bubbles" up through the DOM hierarchy to the parent element. The event listener on the parent element can then check the event.target property to determine which child element triggered the event.

### Event loop

Event loop is a fundamental conecpt in JavaScript that allows for asynchronous programmind despite Javascrpt being a single-threaded.

## F

### Function
A function is a block of reusable code that performs a specific task or calculates a value. Functions allow you to organize code into logical units, making it easier to understand, debug, and maintain.

## I

### IIFE
An Immediately Invoked Function Expression (IIFE) is a JavaScript design pattern that involves defining and immediately executing a function. This pattern is often used to create a private scope for variables and functions, preventing them from polluting the global namespace.

### Inheritance
A way to create a new object or class that uses properties and methods from an existing object or class.

#### Example:
```js
// Parent class
class Animal {
  speak() {
    console.log('Animal makes a sound.');
  }
}
// Child class inherits from Animal
class Dog extends Animal {
  bark() {
    console.log('Dog barks.');
  }
}
const dog = new Dog();
dog.speak(); // Outputs: Animal makes a sound.
dog.bark();  // Outputs: Dog barks.
```

## H

### Hoisting
Hoisting in JavaScript refers to the process where variable and function declarations are moved to the top of their containing scope during the compilation phase. This means you can use variables and functions before they are declared in the code.
For variables declared with var, the declaration is hoisted, but the initialization is not.
For variables declared with let and const, the declaration is hoisted, but they are not initialized until the code execution reaches the declaration. This results in a "temporal dead zone" where accessing the variable before its declaration will throw a ReferenceError.

## M

### Map
A collection of key-value pairs where both keys and values can be of any type. Keys are unique and are maintained in insertion order.


## N

### Null
null is a primitive value, it represents the intentional absence of any value. It's often used to explicitly indicate that a variable or object property does not have a value.


## P

### Promise
A Promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. Promises provide a cleaner and more flexible way to work with asynchronous code compared to traditional callback-based approaches.

### Parameters
 Variables listed as part of the function definition.

### prototypal inheritance
In JavaScript, prototypal inheritance allows objects to inherit properties and methods from other objects.

## S

### Set
A collection of unique values where each value can only occur once. Values are maintained in insertion order.

### Statements
Statements are syntax constructs and commands that perform actions.

## T

### Template Literal
A string literal allowing embedded expressions, multi-line strings, and variable interpolation using backticks (\` \`).

## U

### Undefined
undefined is a primitive value in JavaScript that is automatically assigned to variables that have not been initialized or to object properties that do not exist.

## V

### Variable
A variable is a named storage location that holds data. In JavaScript, variables can store various types of data, including numbers, strings, objects, and functions. Variables can be declared using the `var`, `let`, or `const` keywords.



## == (Loose Equality)
Compares two values for equality after converting both to a common type.

## === (Strict Equality)
Compares two values for equality without type conversion; both type and value must match.

## ? (Conditional/Ternary Operator)
A shorthand for `if-else` statements, returning one value if a condition is true and another if false.

## && (Logical AND)
Returns true if both operands are true; otherwise, returns false.

## ! (Logical NOT)
Inverts the truthiness of the operand; true becomes false, and false becomes true.
