### What is the difference between `==` and `===` in JavaScript?

**==** checks for equality of values, but it performs type coercion, which means it may convert the operands to the same type before making the comparison. For example, 0 **==** false would return true because both are coerced to a boolean value.

**===** also checks for equality of values, but it does not perform type coercion. It compares both the values and the data types. This means 0 **===** false would return false because they are of different types.

**==** checks for equality after type coercion.
**===** checks for equality without type coercion.

<hr>

### What is the difference between let, const, and var in JavaScript?

1. `let` is used to declare block-scoped variables. Variables declared with `let` are not hoisted, meaning they are not accessible before the line of code where they are declared.

2. `const` also declares block-scoped variables. Variables declared with `const` cannot be reassigned after they are initialized, but the value they hold can still be mutated if it is mutable (e.g., an array or object).

3. `var` declares variables with function scope (or globally scoped if declared outside of a function). Variables declared with `var` are hoisted, meaning they are accessible throughout the entire function or global scope, regardless of where they are declared within that scope.

<hr>

### What is the event loop in JavaScript and how does it work?

The event loop is a fundamental concept in JavaScript that allows for asynchronous programming despite JavaScript being a single-threaded programming language.

It works in stages:

1. **Call Stack**: This is where code is executed. Functions get pushed onto the stack when they are called and popped off when they return a value.

2. **Web APIs**: Browsers provide web APIs for tasks like making HTTP requests, timers, and event listeners. When an asynchronous operation is initiated, the function is offloaded to these APIs.

3. **Callback Queue**: Once an asynchronous operation is completed, its callback is placed in the callback queue.

4. **Event Loop**: The event loop constantly checks the call stack. If it is empty, it moves callbacks from the callback queue to the call stack for execution.

<hr>

### What is the difference between null and undefined in JavaScript?

1. `undefined` typically represents the absence of a value. It is automatically assigned to a variable by JavaScript when a variable is declared but not initialized, or when accessing an object property that does not exist.
2. `null`, on the other hand, represents the intentional absence of any value. It is a value that can be assigned to a variable to explicitly indicate that it has no value.

<hr>

### Explain what the this keyword refers to in JavaScript and how its value is determined

In JavaScript, the value of the `this` keyword refers to the object from which a function is called. It dynamically binds to different values based on how the function is invoked. The value of `this` is determined by the execution context in which the function is called. Here are a few common scenarios:

1. When a function is called as a method of an object, `this` refers to the object itself.
2. When a function is called as a standalone function, `this` refers to the global object (`window` in a browser, `global` in Node.js) in non-strict mode, and `undefined` in strict mode.
3. When a function is called using the `new` keyword to create an instance of a constructor function, `this` refers to the newly created object.
4. When a function is called using the `call()` or `apply()` method, `this` is explicitly set to the value passed as the first argument to `call()` or `apply()`.

Understanding the context in which a function is called is crucial for determining the value of `this` in JavaScript.

<hr>

### What are JavaScript Promises, and how do they work?

A Promise is an object that represents the eventual completion (or failure) of an asynchronous operation and its resulting value. Promises provide a cleaner and more powerful way to handle asynchronous operations compared to traditional callback-based approaches.

A Promise has three states:

1. **Pending**: The initial state, neither fulfilled nor rejected.
2. **Fulfilled**: The operation completed successfully, and the promise has a resulting value.
3. **Rejected**: The operation failed, and the promise has a reason for the failure (an error).

A Promise is created using the `Promise` constructor, which takes a function (executor) with two arguments: `resolve` and `reject`. These functions are used to indicate the outcome of the operation.

Here's a basic example:

```javascript
let myPromise = new Promise((resolve, reject) => {
  let success = true; // Simulating success or failure

  if (success) {
    resolve("Operation was successful!"); // The promise is fulfilled
  } else {
    reject("Operation failed."); // The promise is rejected
  }
});

myPromise
  .then(result => {
    console.log(result); // Handle the fulfillment
  })
  .catch(error => {
    console.error(error); // Handle the rejection
  });
 
```

 <hr>

### What is the difference between call(), apply(), and bind() methods in JavaScript?

**`call()`, `apply()`, and `bind()` are methods that allow you to set the value of `this` inside a function and invoke that function in different ways.**

1. **`call()`**:
   1. Syntax: `functionName.call(thisArg, arg1, arg2, ...)`
   1. `call()` method calls a function with a given `this` value and arguments provided individually.
   1. Example:

     ```javascript
     function greet(greeting, punctuation) {
       console.log(greeting + ', ' + this.name + punctuation);
     }

     const person = { name: 'Alice' };

     greet.call(person, 'Hello', '!'); // Output: "Hello, Alice!"
     ```

2. **`apply()`**:
   1. Syntax: `functionName.apply(thisArg, [argsArray])`
   1. `apply()` method calls a function with a given `this` value and arguments provided as an array (or an array-like object).
   1. Example:

     ```javascript
     function greet(greeting, punctuation) {
       console.log(greeting + ', ' + this.name + punctuation);
     }

     const person = { name: 'Alice' };

     greet.apply(person, ['Hello', '!']); // Output: "Hello, Alice!"
     ```

3. **`bind()`**:
   1. Syntax: `functionName.bind(thisArg, arg1, arg2, ...)`
   1. `bind()` method creates a new function that, when called, has its `this` value set to the provided value, with a given sequence of arguments preceding any provided when the new function is called.
   1. Unlike `call()` and `apply()`, `bind()` does not immediately invoke the function. Instead, it returns a new function.
   1. Example:

     ```javascript
     function greet(greeting, punctuation) {
       console.log(greeting + ', ' + this.name + punctuation);
     }

     const person = { name: 'Alice' };

     const greetPerson = greet.bind(person, 'Hello');
     greetPerson('!'); // Output: "Hello, Alice!"
     ```

<hr>

### What is the difference between synchronous and asynchronous programming in JavaScript?

**Synchronous programming**:

1. In synchronous programming, code is executed sequentially, line by line. Each operation must complete before the next one starts.
1. If an operation takes a long time (e.g., a network request or a long computation), it blocks the execution of subsequent operations until it finishes.
1. Example:

  ```javascript
  console.log('Start');
  // This represents a long-running operation
  for (let i = 0; i < 1e9; i++) {}
  console.log('End');
  // Output: 'Start', (delay), 'End'
  ```

**Asynchronous programming**:

1. In asynchronous programming, some operations (like network requests or timers) are executed in the background, allowing the main program to continue running.
1. This prevents blocking and allows the program to remain responsive.
1. Asynchronous code often uses callbacks, promises, or async/await to handle the completion of these operations.

```javascript
console.log('Start');
setTimeout(() => {
  console.log('Async operation complete');
}, 1000);
console.log('End');
// Output: 'Start', 'End', 'Async operation complete'

```

<hr>

### What is the difference between `map()`, `filter()`, and `reduce()` methods in JavaScript?

**Answer:**

#### `map()`

1. **Description**: The `map()` method creates a new array populated with the results of calling a provided function on every element in the calling array.
1. **Example**:

  ```javascript
  const numbers = [1, 2, 3, 4];
  const doubled = numbers.map(num => num * 2);
  console.log(doubled); // Output: [2, 4, 6, 8]
```

#### filter()

1. **Description**: The filter() method creates a new array with all elements that pass the test implemented by the provided function.
1. **Example**:

```javascript
const numbers = [1, 2, 3, 4];
const evens = numbers.filter(num => num % 2 === 0);
console.log(evens); // Output: [2, 4]
```

#### reduce()

1. **Description**: The reduce() method executes a reducer function (that you provide) on each element of the array, resulting in a single output value.

1. **Example**:

```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
console.log(sum); // Output: 10
```

**Question:** What are the different ways to create objects in JavaScript?

**Answer:**

### Different Ways to Create Objects in JavaScript

1. **Object Literal Syntax**
   - This is the most common and simplest way to create an object.
   - Example:

     ```javascript
     let obj = {};
     ```

2. **`Object.create()` Method**
   - This method creates a new object with the specified prototype object and properties.
   - Example:

     ```javascript
     let objCreate = Object.create({});
     ```

3. **`new Object()` Syntax**
   - This method creates an instance of the `Object` type.
   - Example:

     ```javascript
     let newObj = new Object();
     ```

4. **Constructor Functions**
   - A constructor function is used to create multiple instances of an object with the same properties and methods.
   - Example:

     ```javascript
     function Person(name, age) {
       this.name = name;
       this.age = age;
     }

     let person1 = new Person('Alice', 30);
     let person2 = new Person('Bob', 25);
     ```

5. **ES6 Classes**
   - Classes are a syntactical sugar over constructor functions and provide a more intuitive way to create objects and handle inheritance.
   - Example:

     ```javascript
     class Person {
       constructor(name, age) {
         this.name = name;
         this.age = age;
       }

       greet() {
         console.log(`Hello, my name is ${this.name}`);
       }
     }

     let person1 = new Person('Alice', 30);
     let person2 = new Person('Bob', 25);
     ```

6. **Factory Functions**
   - A factory function returns a new object every time it is called.
   - Example:

     ```javascript
     function createPerson(name, age) {
       return {
         name: name,
         age: age,
         greet() {
           console.log(`Hello, my name is ${this.name}`);
         }
       };
     }

     let person1 = createPerson('Alice', 30);
     let person2 = createPerson('Bob', 25);
     ```

<hr>

### What are arrow functions in JavaScript, and how do they differ from regular functions?

**Arrow functions** are a shorter syntax for writing functions in JavaScript. They are anonymous and lexically bind the `this` value, meaning `this` inside an arrow function refers to the context in which the function was defined, not the context from which it was called.

#### Syntax

```javascript
// Regular function
function add(a, b) {
  return a + b;
}

// Arrow function
const add = (a, b) => a + b;
```

#### Key Differences from Regular Functions

1. **Syntax:** Arrow functions have a more concise syntax.
1. **this Binding:** In regular functions, `this` refers to the object that called the function, which could change depending on how the function is called. In arrow functions, `this` is lexically bound to the surrounding context.

```javascript
function Person() {
  this.age = 0;

  setInterval(function growUp() {
    this.age++; // `this` refers to the global object, not the instance of Person
  }, 1000);
}

function Person() {
  this.age = 0;

  setInterval(() => {
    this.age++; // `this` refers to the instance of Person
  }, 1000);
}

```

 3. **arguments Object:** Arrow functions do not have their own arguments object. If you need to access the arguments object, you need to use a regular function.

 ```javascript
 // Regular function
function sum() {
  return Array.from(arguments).reduce((acc, val) => acc + val, 0);
}

// Arrow function (doesn't have `arguments` object)
const sum = () => {
  // `arguments` object is not available here
};
```

 4. **Cannot be used as constructors:** Arrow functions cannot be used with the `new` keyword. They do not have a `prototype` property.

 ```javascript
// Regular function
function Car(make, model) {
  this.make = make;
  this.model = model;
}

const myCar = new Car('Toyota', 'Corolla'); // Works fine

// Arrow function
const Car = (make, model) => {
  this.make = make;
  this.model = model;
};

const myCar = new Car('Toyota', 'Corolla'); // TypeError: Car is not a constructor

 ```

### What is the `async`/`await` syntax in JavaScript, and how does it improve working with Promises?

**`async`/`await`** is a syntactic sugar introduced in ES2017 that makes it easier to work with Promises, providing a cleaner and more readable way to write asynchronous code compared to the traditional `.then()` and `.catch()` methods.

#### `async` Keyword

- The `async` keyword is used to declare an asynchronous function. An async function always returns a Promise.
- If the function returns a value, the Promise will be resolved with that value.
- If the function throws an error, the Promise will be rejected with that error.

#### `await` Keyword

- The `await` keyword can only be used inside an async function.
- It pauses the execution of the async function and waits for the Promise to resolve.
- Once the Promise is resolved, it returns the resolved value.
- If the Promise is rejected, it throws the error.

#### Example

**Using Promises:**

```javascript
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('Data received');
    }, 2000);
  });
}

fetchData()
  .then(data => {
    console.log(data); // Output after 2 seconds: Data received
  })
  .catch(error => {
    console.error(error);
  });
```

**Using `asnc`/`await`:**

```javascript

async function fetchDataAsync() {
  try {
    const data = await fetchData();
    console.log(data); // Output after 2 seconds: Data received
  } catch (error) {
    console.error(error);
  }
}

fetchDataAsync();

```

#### Advantages of `async`/`await`

1. **Readability**: Makes the asynchronous code look synchronous, which is easier to read and understand.
2. **Error Handling**: Can use `try...catch` blocks for error handling, making it more consistent with synchronous code.
3. **Simplified Syntax**: Reduces the need for chaining `.then()` and `.catch()` methods, which can become difficult to read with multiple nested asynchronous operations.


**Question:** Explain the concept of event bubbling and event capturing in JavaScript.

**Answer:**

### Event Bubbling and Event Capturing in JavaScript

**Event Bubbling**:
- When an event occurs on an element, it will bubble up through its ancestors in the DOM tree, triggering any event listeners attached to those elements.
- This means that if an event listener is attached to a parent element, it will also be triggered when the same event occurs on a child element.
- Bubbling occurs from the target element up to the root of the DOM tree (HTML element).

**Event Capturing**:
- Event capturing is the opposite of event bubbling.
- When an event occurs, it starts from the root of the DOM tree and travels down to the target element.
- This allows you to intercept events at an ancestor level before they reach the target element.
- Event capturing is less commonly used than event bubbling, but it can be useful in certain scenarios, such as global event handling.
