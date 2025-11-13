# JavaScript Guide 🚀

Welcome to your complete guide to JavaScript! This guide will teach you everything you need to know to start programming interactive web applications and beyond.

## Table of Contents
- [What is JavaScript?](#what-is-javascript)
- [How to Add JavaScript](#how-to-add-javascript)
- [JavaScript Syntax](#javascript-syntax)
- [Variables and Data Types](#variables-and-data-types)
- [Operators](#operators)
- [Functions](#functions)
- [Control Structures](#control-structures)
- [Arrays](#arrays)
- [Objects](#objects)
- [DOM Manipulation](#dom-manipulation)
- [Events](#events)
- [Asynchronous JavaScript](#asynchronous-javascript)
- [Error Handling](#error-handling)
- [ES6+ Features](#es6-features)
- [Classes and OOP](#classes-and-oop)
- [Modules](#modules)
- [APIs and Fetch](#apis-and-fetch)
- [Best Practices](#best-practices)
- [Practice Exercises](#practice-exercises)

---

## What is JavaScript?

JavaScript is a **high-level, interpreted programming language** that makes web pages interactive. Originally created for web browsers, JavaScript now runs everywhere - servers, mobile apps, desktop applications, and more.

### Key Points:
- JavaScript adds **interactivity** to web pages
- It's a **client-side** and **server-side** language
- JavaScript is **dynamic** and **flexible**
- It's one of the most popular programming languages

### What JavaScript Can Do:
- Respond to user interactions (clicks, typing, etc.)
- Modify HTML and CSS dynamically
- Validate form data
- Create animations and effects
- Communicate with servers (AJAX)
- Build complete web applications
- Create mobile and desktop apps

---

## How to Add JavaScript

There are three ways to add JavaScript to your web pages:

### 1. Inline JavaScript (Not Recommended)
```html
<button onclick="alert('Hello!')">Click me</button>
```

### 2. Internal JavaScript
```html
<head>
    <script>
        function greet() {
            alert('Hello World!');
        }
    </script>
</head>
```

### 3. External JavaScript (Best Practice)
```html
<!-- In your HTML file -->
<head>
    <script src="script.js"></script>
</head>
<!-- Or before closing body tag -->
<body>
    <!-- Your HTML content -->
    <script src="script.js"></script>
</body>
```

```javascript
// In your script.js file
function greet() {
    alert('Hello World!');
}
```

---

## JavaScript Syntax

### Basic Syntax Rules
```javascript
// Single line comment
/* 
   Multi-line comment
   Can span multiple lines
*/

// Statements end with semicolons (optional but recommended)
let message = "Hello World!";
console.log(message);

// JavaScript is case-sensitive
let myVariable = 5;
let MyVariable = 10; // Different variable!

// Strings can use single or double quotes
let str1 = "Hello";
let str2 = 'World';
let str3 = `Template literal with ${str1}`;
```

### Output and Debugging
```javascript
// Console output (for debugging)
console.log("Hello World!");
console.error("This is an error");
console.warn("This is a warning");

// Alert boxes (avoid in production)
alert("Hello!");
confirm("Are you sure?");
let userInput = prompt("Enter your name:");

// Writing to HTML document
document.write("Hello World!");

// Writing to HTML element
document.getElementById("demo").innerHTML = "Hello World!";
```

---

## Variables and Data Types

### Variable Declarations
```javascript
// var (old way - avoid)
var oldWay = "Don't use this";

// let (block-scoped, can be reassigned)
let age = 25;
age = 26; // OK

// const (block-scoped, cannot be reassigned)
const name = "John";
// name = "Jane"; // Error!

// const with objects (object can be modified)
const person = { name: "John" };
person.age = 30; // OK - modifying property
// person = {}; // Error - reassigning variable
```

### Data Types

#### Primitive Types
```javascript
// Number (integers and decimals)
let integer = 42;
let decimal = 3.14159;
let negative = -10;
let infinity = Infinity;
let notANumber = NaN;

// String
let greeting = "Hello World!";
let singleQuotes = 'Hello World!';
let templateLiteral = `Hello ${name}!`;

// Boolean
let isTrue = true;
let isFalse = false;

// Undefined
let undefinedVar;
console.log(undefinedVar); // undefined

// Null
let nullVar = null;

// Symbol (ES6)
let sym = Symbol('id');

// BigInt (ES2020)
let bigNumber = 1234567890123456789012345678901234567890n;
```

#### Non-Primitive Types
```javascript
// Object
let person = {
    name: "John",
    age: 30,
    city: "New York"
};

// Array
let numbers = [1, 2, 3, 4, 5];
let mixed = ["Hello", 42, true, null];

// Function
function greet() {
    return "Hello!";
}

// Date
let now = new Date();

// RegExp
let pattern = /hello/i;
```

### Type Checking and Conversion
```javascript
// Type checking
console.log(typeof "Hello");    // "string"
console.log(typeof 42);         // "number"
console.log(typeof true);       // "boolean"
console.log(typeof undefined);  // "undefined"
console.log(typeof null);       // "object" (JavaScript quirk!)
console.log(typeof {});         // "object"
console.log(typeof []);         // "object"

// Better array check
console.log(Array.isArray([])); // true

// Type conversion
let str = "123";
let num = Number(str);          // 123
let num2 = parseInt(str);       // 123
let num3 = parseFloat("3.14");  // 3.14

let numToStr = String(123);     // "123"
let numToStr2 = (123).toString(); // "123"

let boolToStr = Boolean(1);     // true
let boolToStr2 = Boolean(0);    // false
```

---

## Operators

### Arithmetic Operators
```javascript
let a = 10;
let b = 3;

console.log(a + b);  // 13 (Addition)
console.log(a - b);  // 7  (Subtraction)
console.log(a * b);  // 30 (Multiplication)
console.log(a / b);  // 3.333... (Division)
console.log(a % b);  // 1  (Modulus/Remainder)
console.log(a ** b); // 1000 (Exponentiation)

// Increment and Decrement
let count = 5;
count++;        // 6 (Post-increment)
++count;        // 7 (Pre-increment)
count--;        // 6 (Post-decrement)
--count;        // 5 (Pre-decrement)
```

### Assignment Operators
```javascript
let x = 10;

x += 5;  // x = x + 5;  (15)
x -= 3;  // x = x - 3;  (12)
x *= 2;  // x = x * 2;  (24)
x /= 4;  // x = x / 4;  (6)
x %= 4;  // x = x % 4;  (2)
x **= 3; // x = x ** 3; (8)
```

### Comparison Operators
```javascript
let a = 5;
let b = "5";

// Equality (with type coercion)
console.log(a == b);   // true (5 == "5")
console.log(a != b);   // false

// Strict equality (no type coercion)
console.log(a === b);  // false (5 !== "5")
console.log(a !== b);  // true

// Relational operators
console.log(a > 3);    // true
console.log(a < 10);   // true
console.log(a >= 5);   // true
console.log(a <= 4);   // false
```

### Logical Operators
```javascript
let isTrue = true;
let isFalse = false;

// AND (&&)
console.log(isTrue && isFalse);  // false

// OR (||)
console.log(isTrue || isFalse);  // true

// NOT (!)
console.log(!isTrue);            // false
console.log(!isFalse);           // true

// Short-circuit evaluation
let name = user && user.name;    // Only access name if user exists
let greeting = name || "Guest";  // Use "Guest" if name is falsy
```

### Ternary Operator
```javascript
// condition ? valueIfTrue : valueIfFalse
let age = 20;
let status = age >= 18 ? "adult" : "minor";

// Can be chained
let score = 85;
let grade = score >= 90 ? "A" : score >= 80 ? "B" : score >= 70 ? "C" : "F";
```

---

## Functions

### Function Declaration
```javascript
function greet(name) {
    return `Hello, ${name}!`;
}

// Call the function
let message = greet("Alice");
console.log(message); // "Hello, Alice!"
```

### Function Expression
```javascript
const greet = function(name) {
    return `Hello, ${name}!`;
};
```

### Arrow Functions (ES6)
```javascript
// Basic arrow function
const greet = (name) => {
    return `Hello, ${name}!`;
};

// Shorter syntax (single parameter, single expression)
const greet2 = name => `Hello, ${name}!`;

// Multiple parameters
const add = (a, b) => a + b;

// No parameters
const sayHello = () => "Hello World!";

// Multiple statements
const processUser = (user) => {
    console.log(`Processing ${user.name}`);
    return user.name.toUpperCase();
};
```

### Function Parameters
```javascript
// Default parameters
function greet(name = "World") {
    return `Hello, ${name}!`;
}

// Rest parameters
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3, 4)); // 10

// Destructuring parameters
function printUser({ name, age, city = "Unknown" }) {
    console.log(`${name}, ${age}, from ${city}`);
}
printUser({ name: "John", age: 30 });
```

### Higher-Order Functions
```javascript
// Function that returns a function
function createMultiplier(factor) {
    return function(number) {
        return number * factor;
    };
}
const double = createMultiplier(2);
console.log(double(5)); // 10

// Function that accepts a function
function processArray(arr, callback) {
    return arr.map(callback);
}
const numbers = [1, 2, 3, 4];
const doubled = processArray(numbers, x => x * 2);
```

---

## Control Structures

### Conditional Statements
```javascript
// if statement
let age = 20;
if (age >= 18) {
    console.log("You are an adult");
}

// if-else statement
if (age >= 18) {
    console.log("You are an adult");
} else {
    console.log("You are a minor");
}

// if-else if-else
let score = 85;
if (score >= 90) {
    console.log("A grade");
} else if (score >= 80) {
    console.log("B grade");
} else if (score >= 70) {
    console.log("C grade");
} else {
    console.log("F grade");
}

// switch statement
let day = "Monday";
switch (day) {
    case "Monday":
        console.log("Start of work week");
        break;
    case "Tuesday":
    case "Wednesday":
    case "Thursday":
        console.log("Middle of work week");
        break;
    case "Friday":
        console.log("TGIF!");
        break;
    default:
        console.log("Weekend!");
}
```

### Loops
```javascript
// for loop
for (let i = 0; i < 5; i++) {
    console.log(i); // 0, 1, 2, 3, 4
}

// for...in loop (for object properties)
let person = { name: "John", age: 30, city: "NYC" };
for (let key in person) {
    console.log(`${key}: ${person[key]}`);
}

// for...of loop (for iterable objects)
let numbers = [1, 2, 3, 4, 5];
for (let number of numbers) {
    console.log(number);
}

// while loop
let count = 0;
while (count < 3) {
    console.log(count);
    count++;
}

// do-while loop
let num = 0;
do {
    console.log(num);
    num++;
} while (num < 3);

// Loop control
for (let i = 0; i < 10; i++) {
    if (i === 3) continue; // Skip this iteration
    if (i === 7) break;    // Exit the loop
    console.log(i); // 0, 1, 2, 4, 5, 6
}
```

---

## Arrays

### Creating Arrays
```javascript
// Array literal (preferred)
let fruits = ["apple", "banana", "orange"];
let numbers = [1, 2, 3, 4, 5];
let mixed = ["hello", 42, true, null];

// Array constructor
let arr = new Array(5);        // Array with 5 empty slots
let arr2 = new Array(1, 2, 3); // [1, 2, 3]

// Array.from()
let chars = Array.from("hello"); // ["h", "e", "l", "l", "o"]
let range = Array.from({ length: 5 }, (_, i) => i + 1); // [1, 2, 3, 4, 5]
```

### Array Methods
```javascript
let fruits = ["apple", "banana", "orange"];

// Adding elements
fruits.push("grape");           // Add to end: ["apple", "banana", "orange", "grape"]
fruits.unshift("mango");        // Add to beginning: ["mango", "apple", "banana", "orange", "grape"]

// Removing elements
let lastFruit = fruits.pop();   // Remove from end: "grape"
let firstFruit = fruits.shift(); // Remove from beginning: "mango"

// Finding elements
let index = fruits.indexOf("banana");     // 1
let includes = fruits.includes("apple");  // true
let found = fruits.find(fruit => fruit.startsWith("o")); // "orange"
let foundIndex = fruits.findIndex(fruit => fruit.startsWith("o")); // 2

// Modifying arrays
fruits.splice(1, 1);           // Remove 1 element at index 1
fruits.splice(1, 0, "kiwi");   // Insert "kiwi" at index 1
fruits.sort();                 // Sort alphabetically
fruits.reverse();              // Reverse the array

// Creating new arrays
let upperFruits = fruits.map(fruit => fruit.toUpperCase());
let longFruits = fruits.filter(fruit => fruit.length > 5);
let totalLength = fruits.reduce((sum, fruit) => sum + fruit.length, 0);

// Array iteration
fruits.forEach(fruit => console.log(fruit));
fruits.forEach((fruit, index) => console.log(`${index}: ${fruit}`));
```

### Advanced Array Methods
```javascript
let numbers = [1, 2, 3, 4, 5];

// map - transform each element
let doubled = numbers.map(x => x * 2); // [2, 4, 6, 8, 10]

// filter - select elements that meet condition
let evens = numbers.filter(x => x % 2 === 0); // [2, 4]

// reduce - combine elements into single value
let sum = numbers.reduce((acc, x) => acc + x, 0); // 15
let max = numbers.reduce((max, x) => x > max ? x : max); // 5

// some - check if at least one element meets condition
let hasEven = numbers.some(x => x % 2 === 0); // true

// every - check if all elements meet condition
let allPositive = numbers.every(x => x > 0); // true

// find - get first element that meets condition
let firstEven = numbers.find(x => x % 2 === 0); // 2

// Chaining methods
let result = numbers
    .filter(x => x > 2)
    .map(x => x * 2)
    .reduce((sum, x) => sum + x, 0); // (3+4+5)*2 = 24
```

### Array Destructuring
```javascript
let fruits = ["apple", "banana", "orange"];

// Basic destructuring
let [first, second, third] = fruits;
console.log(first);  // "apple"
console.log(second); // "banana"

// Skip elements
let [firstFruit, , thirdFruit] = fruits;

// Rest operator
let [head, ...tail] = fruits;
console.log(head); // "apple"
console.log(tail); // ["banana", "orange"]

// Default values
let [a, b, c, d = "default"] = fruits;
console.log(d); // "default"
```

---

## Objects

### Creating Objects
```javascript
// Object literal (most common)
let person = {
    name: "John",
    age: 30,
    city: "New York",
    isMarried: false
};

// Constructor function
function Person(name, age) {
    this.name = name;
    this.age = age;
}
let john = new Person("John", 30);

// Object.create()
let personPrototype = {
    greet: function() {
        return `Hello, I'm ${this.name}`;
    }
};
let mary = Object.create(personPrototype);
mary.name = "Mary";

// Class (ES6)
class PersonClass {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
}
let bob = new PersonClass("Bob", 25);
```

### Object Properties and Methods
```javascript
let person = {
    firstName: "John",
    lastName: "Doe",
    age: 30,
    
    // Method
    getFullName: function() {
        return `${this.firstName} ${this.lastName}`;
    },
    
    // ES6 method shorthand
    greet() {
        return `Hello, I'm ${this.getFullName()}`;
    }
};

// Accessing properties
console.log(person.firstName);        // Dot notation
console.log(person["lastName"]);      // Bracket notation
console.log(person.getFullName());    // Method call

// Adding properties
person.email = "john@email.com";
person["phone"] = "123-456-7890";

// Deleting properties
delete person.age;

// Property existence
console.log("name" in person);              // false
console.log(person.hasOwnProperty("name")); // false
console.log("email" in person);             // true
```

### Object Methods
```javascript
let person = { name: "John", age: 30, city: "NYC" };

// Get keys, values, entries
let keys = Object.keys(person);       // ["name", "age", "city"]
let values = Object.values(person);   // ["John", 30, "NYC"]
let entries = Object.entries(person); // [["name", "John"], ["age", 30], ["city", "NYC"]]

// Object.assign() - merge objects
let defaults = { theme: "dark", lang: "en" };
let userPrefs = { theme: "light" };
let settings = Object.assign({}, defaults, userPrefs); // { theme: "light", lang: "en" }

// Spread operator (ES6)
let newSettings = { ...defaults, ...userPrefs }; // Same result as above

// Object.freeze() - make immutable
Object.freeze(person);
// person.name = "Jane"; // Won't work

// Object.seal() - prevent adding/removing properties
Object.seal(person);
// person.email = "test"; // Won't work
// person.name = "Jane";  // Still works
```

### Object Destructuring
```javascript
let person = { name: "John", age: 30, city: "NYC", email: "john@email.com" };

// Basic destructuring
let { name, age } = person;
console.log(name); // "John"
console.log(age);  // 30

// Rename variables
let { name: firstName, age: years } = person;
console.log(firstName); // "John"
console.log(years);     // 30

// Default values
let { name, age, country = "USA" } = person;
console.log(country); // "USA"

// Rest operator
let { name, ...rest } = person;
console.log(rest); // { age: 30, city: "NYC", email: "john@email.com" }

// Nested destructuring
let user = {
    name: "John",
    address: {
        street: "123 Main St",
        city: "NYC"
    }
};
let { address: { street, city } } = user;
```

---

## DOM Manipulation

### Selecting Elements
```javascript
// By ID
let element = document.getElementById("myId");

// By class name
let elements = document.getElementsByClassName("myClass");
let element = elements[0]; // Get first element

// By tag name
let paragraphs = document.getElementsByTagName("p");

// Query selectors (preferred)
let element = document.querySelector("#myId");           // First element with ID
let element = document.querySelector(".myClass");        // First element with class
let element = document.querySelector("div.container");   // First div with class container
let elements = document.querySelectorAll(".myClass");    // All elements with class
let elements = document.querySelectorAll("li");          // All li elements
```

### Modifying Elements
```javascript
let element = document.querySelector("#myElement");

// Change content
element.innerHTML = "<strong>Bold text</strong>";  // HTML content
element.textContent = "Plain text only";           // Text content only
element.innerText = "Visible text only";           // Visible text (respects CSS)

// Change attributes
element.setAttribute("class", "newClass");
element.setAttribute("data-id", "123");
let className = element.getAttribute("class");
element.removeAttribute("data-id");

// Direct property access
element.id = "newId";
element.className = "class1 class2";
element.src = "newimage.jpg";  // For img elements
element.href = "https://example.com"; // For a elements

// Change styles
element.style.color = "red";
element.style.backgroundColor = "blue";
element.style.fontSize = "18px";
element.style.display = "none"; // Hide element
element.style.display = "block"; // Show element

// CSS classes
element.classList.add("newClass");
element.classList.remove("oldClass");
element.classList.toggle("active");
element.classList.contains("myClass"); // true/false
```

### Creating and Adding Elements
```javascript
// Create new element
let newDiv = document.createElement("div");
newDiv.textContent = "Hello World";
newDiv.className = "myClass";

// Create text node
let textNode = document.createTextNode("Just text");

// Add to DOM
let container = document.querySelector("#container");
container.appendChild(newDiv);           // Add as last child
container.insertBefore(newDiv, container.firstChild); // Add as first child

// Insert adjacent
let element = document.querySelector("#target");
element.insertAdjacentHTML("beforebegin", "<p>Before element</p>");
element.insertAdjacentHTML("afterbegin", "<p>First child</p>");
element.insertAdjacentHTML("beforeend", "<p>Last child</p>");
element.insertAdjacentHTML("afterend", "<p>After element</p>");

// Remove elements
element.remove();                        // Remove element itself
container.removeChild(element);          // Remove child element
```

### Traversing the DOM
```javascript
let element = document.querySelector("#myElement");

// Parent
let parent = element.parentNode;
let parent = element.parentElement;

// Children
let children = element.children;         // HTML elements only
let childNodes = element.childNodes;     // All nodes (including text)
let firstChild = element.firstElementChild;
let lastChild = element.lastElementChild;

// Siblings
let nextSibling = element.nextElementSibling;
let prevSibling = element.previousElementSibling;

// Find elements within
let found = element.querySelector(".childClass");
let allFound = element.querySelectorAll("p");
```

---

## Events

### Adding Event Listeners
```javascript
// Method 1: addEventListener (preferred)
let button = document.querySelector("#myButton");
button.addEventListener("click", function() {
    console.log("Button clicked!");
});

// Arrow function
button.addEventListener("click", () => {
    console.log("Button clicked!");
});

// Named function
function handleClick() {
    console.log("Button clicked!");
}
button.addEventListener("click", handleClick);

// Method 2: HTML attribute (not recommended)
// <button onclick="handleClick()">Click me</button>

// Method 3: Element property
button.onclick = handleClick;
```

### Common Events
```javascript
let element = document.querySelector("#myElement");

// Mouse events
element.addEventListener("click", handleClick);
element.addEventListener("dblclick", handleDoubleClick);
element.addEventListener("mousedown", handleMouseDown);
element.addEventListener("mouseup", handleMouseUp);
element.addEventListener("mouseover", handleMouseOver);
element.addEventListener("mouseout", handleMouseOut);
element.addEventListener("mousemove", handleMouseMove);

// Keyboard events
document.addEventListener("keydown", handleKeyDown);
document.addEventListener("keyup", handleKeyUp);
document.addEventListener("keypress", handleKeyPress);

// Form events
let form = document.querySelector("#myForm");
let input = document.querySelector("#myInput");

form.addEventListener("submit", handleSubmit);
input.addEventListener("change", handleChange);
input.addEventListener("input", handleInput);  // Real-time changes
input.addEventListener("focus", handleFocus);
input.addEventListener("blur", handleBlur);

// Window events
window.addEventListener("load", handleLoad);
window.addEventListener("resize", handleResize);
window.addEventListener("scroll", handleScroll);
```

### Event Object
```javascript
button.addEventListener("click", function(event) {
    // Prevent default behavior
    event.preventDefault();
    
    // Stop event bubbling
    event.stopPropagation();
    
    // Event properties
    console.log(event.type);        // "click"
    console.log(event.target);      // Element that triggered event
    console.log(event.currentTarget); // Element that event listener is attached to
    console.log(event.clientX);     // Mouse X coordinate
    console.log(event.clientY);     // Mouse Y coordinate
});

// Keyboard events
document.addEventListener("keydown", function(event) {
    console.log(event.key);         // "Enter", "a", "ArrowUp", etc.
    console.log(event.keyCode);     // Numeric key code (deprecated)
    console.log(event.ctrlKey);     // true if Ctrl key is pressed
    console.log(event.shiftKey);    // true if Shift key is pressed
    console.log(event.altKey);      // true if Alt key is pressed
});
```

### Event Delegation
```javascript
// Instead of adding listeners to each item
let items = document.querySelectorAll(".item");
items.forEach(item => {
    item.addEventListener("click", handleItemClick);
});

// Use event delegation (more efficient)
let container = document.querySelector("#container");
container.addEventListener("click", function(event) {
    if (event.target.classList.contains("item")) {
        handleItemClick(event);
    }
});

// This works for dynamically added elements too!
```

### Removing Event Listeners
```javascript
// To remove, you need the exact same function reference
function handleClick() {
    console.log("Clicked!");
}

// Add listener
button.addEventListener("click", handleClick);

// Remove listener
button.removeEventListener("click", handleClick);

// Anonymous functions can't be removed!
// button.addEventListener("click", () => {}); // Can't remove this
```

---

## Asynchronous JavaScript

### Callbacks
```javascript
// Callback function
function fetchData(callback) {
    setTimeout(() => {
        let data = { name: "John", age: 30 };
        callback(data);
    }, 1000);
}

// Using the callback
fetchData(function(data) {
    console.log("Data received:", data);
});

// Callback hell (avoid this!)
fetchUser(function(user) {
    fetchPosts(user.id, function(posts) {
        fetchComments(posts[0].id, function(comments) {
            // Too many nested callbacks!
        });
    });
});
```

### Promises
```javascript
// Creating a promise
function fetchData() {
    return new Promise((resolve, reject) => {
        setTimeout(() => {
            let success = true;
            if (success) {
                resolve({ name: "John", age: 30 });
            } else {
                reject(new Error("Failed to fetch data"));
            }
        }, 1000);
    });
}

// Using promises
fetchData()
    .then(data => {
        console.log("Data received:", data);
        return data.name;
    })
    .then(name => {
        console.log("Name:", name);
    })
    .catch(error => {
        console.error("Error:", error.message);
    })
    .finally(() => {
        console.log("Promise completed");
    });

// Promise.all() - wait for all promises
Promise.all([promise1, promise2, promise3])
    .then(results => {
        console.log("All promises resolved:", results);
    })
    .catch(error => {
        console.log("One or more promises failed:", error);
    });

// Promise.race() - first promise to settle
Promise.race([promise1, promise2, promise3])
    .then(result => {
        console.log("First promise resolved:", result);
    });
```

### Async/Await (ES2017)
```javascript
// Async function
async function fetchUserData() {
    try {
        let user = await fetchUser();
        let posts = await fetchPosts(user.id);
        let comments = await fetchComments(posts[0].id);
        
        return { user, posts, comments };
    } catch (error) {
        console.error("Error:", error);
        throw error;
    }
}

// Using async function
fetchUserData()
    .then(data => console.log(data))
    .catch(error => console.error(error));

// Or with async/await
async function main() {
    try {
        let data = await fetchUserData();
        console.log(data);
    } catch (error) {
        console.error(error);
    }
}

// Parallel execution with async/await
async function fetchAllData() {
    try {
        // Sequential (slower)
        let user = await fetchUser();
        let settings = await fetchSettings();
        
        // Parallel (faster)
        let [user2, settings2] = await Promise.all([
            fetchUser(),
            fetchSettings()
        ]);
        
        return { user2, settings2 };
    } catch (error) {
        console.error(error);
    }
}
```

### setTimeout and setInterval
```javascript
// setTimeout - execute once after delay
let timeoutId = setTimeout(() => {
    console.log("This runs after 2 seconds");
}, 2000);

// Clear timeout
clearTimeout(timeoutId);

// setInterval - execute repeatedly
let intervalId = setInterval(() => {
    console.log("This runs every second");
}, 1000);

// Clear interval
clearInterval(intervalId);

// Using with async/await
function delay(ms) {
    return new Promise(resolve => setTimeout(resolve, ms));
}

async function delayedFunction() {
    console.log("Start");
    await delay(2000);
    console.log("After 2 seconds");
}
```

---

## Error Handling

### Try-Catch-Finally
```javascript
try {
    // Code that might throw an error
    let result = riskyOperation();
    console.log(result);
} catch (error) {
    // Handle the error
    console.error("An error occurred:", error.message);
} finally {
    // Always executes (optional)
    console.log("Cleanup code here");
}

// Specific error types
try {
    JSON.parse("invalid json");
} catch (error) {
    if (error instanceof SyntaxError) {
        console.log("JSON syntax error");
    } else if (error instanceof ReferenceError) {
        console.log("Reference error");
    } else {
        console.log("Other error:", error.message);
    }
}
```

### Throwing Errors
```javascript
// Throwing generic error
function divide(a, b) {
    if (b === 0) {
        throw new Error("Division by zero is not allowed");
    }
    return a / b;
}

// Custom error types
class ValidationError extends Error {
    constructor(message) {
        super(message);
        this.name = "ValidationError";
    }
}

function validateEmail(email) {
    if (!email.includes("@")) {
        throw new ValidationError("Invalid email format");
    }
}

// Using custom errors
try {
    validateEmail("invalid-email");
} catch (error) {
    if (error instanceof ValidationError) {
        console.log("Validation failed:", error.message);
    } else {
        console.log("Unexpected error:", error.message);
    }
}
```

### Error Handling with Promises
```javascript
// Promise rejection
function fetchData() {
    return new Promise((resolve, reject) => {
        // Simulate API call
        setTimeout(() => {
            let success = Math.random() > 0.5;
            if (success) {
                resolve("Data loaded successfully");
            } else {
                reject(new Error("Failed to load data"));
            }
        }, 1000);
    });
}

// Handle with .catch()
fetchData()
    .then(data => console.log(data))
    .catch(error => console.error("Error:", error.message));

// Handle with async/await
async function loadData() {
    try {
        let data = await fetchData();
        console.log(data);
    } catch (error) {
        console.error("Error:", error.message);
    }
}
```

---

## ES6+ Features

### Template Literals
```javascript
let name = "John";
let age = 30;

// Template literal with interpolation
let message = `Hello, my name is ${name} and I am ${age} years old.`;

// Multi-line strings
let multiline = `
    This is a
    multi-line
    string
`;

// Expression in template literals
let price = 19.99;
let tax = 0.08;
let total = `Total: $${(price * (1 + tax)).toFixed(2)}`;

// Tagged template literals
function highlight(strings, ...values) {
    return strings.reduce((result, string, i) => {
        return result + string + (values[i] ? `<mark>${values[i]}</mark>` : '');
    }, '');
}

let highlighted = highlight`The price is ${price} with tax ${tax}`;
```

### Destructuring Assignment
```javascript
// Array destructuring
let colors = ["red", "green", "blue"];
let [primary, secondary, tertiary] = colors;

// Object destructuring
let person = { name: "John", age: 30, city: "NYC" };
let { name, age, city } = person;

// Nested destructuring
let user = {
    id: 1,
    profile: {
        name: "John",
        email: "john@email.com"
    }
};
let { profile: { name, email } } = user;

// Function parameter destructuring
function printUser({ name, age = 0, city = "Unknown" }) {
    console.log(`${name}, ${age}, from ${city}`);
}
printUser({ name: "John", age: 30 });
```

### Spread and Rest Operators
```javascript
// Spread with arrays
let arr1 = [1, 2, 3];
let arr2 = [4, 5, 6];
let combined = [...arr1, ...arr2]; // [1, 2, 3, 4, 5, 6]

// Spread with objects
let obj1 = { a: 1, b: 2 };
let obj2 = { c: 3, d: 4 };
let combined = { ...obj1, ...obj2 }; // { a: 1, b: 2, c: 3, d: 4 }

// Rest in function parameters
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}
sum(1, 2, 3, 4); // 10

// Rest in destructuring
let [first, second, ...rest] = [1, 2, 3, 4, 5];
console.log(rest); // [3, 4, 5]
```

### Let and Const vs Var
```javascript
// var - function scoped, hoisted, can be redeclared
function example() {
    var x = 1;
    if (true) {
        var x = 2; // Same variable
        console.log(x); // 2
    }
    console.log(x); // 2
}

// let - block scoped, not hoisted, cannot be redeclared
function example2() {
    let y = 1;
    if (true) {
        let y = 2; // Different variable
        console.log(y); // 2
    }
    console.log(y); // 1
}

// const - block scoped, must be initialized, cannot be reassigned
const PI = 3.14159;
// PI = 3.14; // Error!

const person = { name: "John" };
person.name = "Jane"; // OK - modifying object property
// person = {}; // Error - reassigning variable
```

### Enhanced Object Literals
```javascript
let name = "John";
let age = 30;

// Property shorthand
let person = { name, age }; // Same as { name: name, age: age }

// Method shorthand
let obj = {
    // Old way
    sayHello: function() {
        return "Hello!";
    },
    
    // New way
    sayGoodbye() {
        return "Goodbye!";
    }
};

// Computed property names
let prop = "dynamicProperty";
let obj2 = {
    [prop]: "value",
    [`${prop}2`]: "value2"
};
```

### Default Parameters
```javascript
// Default function parameters
function greet(name = "World", punctuation = "!") {
    return `Hello, ${name}${punctuation}`;
}

greet(); // "Hello, World!"
greet("John"); // "Hello, John!"
greet("John", "?"); // "Hello, John?"

// Default with destructuring
function processOptions({ 
    timeout = 1000, 
    retries = 3, 
    debug = false 
} = {}) {
    console.log(`Timeout: ${timeout}, Retries: ${retries}, Debug: ${debug}`);
}

processOptions(); // Uses all defaults
processOptions({ timeout: 5000 }); // Overrides timeout only
```

---

## Classes and OOP

### Class Declaration
```javascript
class Person {
    // Constructor
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
    
    // Instance methods
    greet() {
        return `Hello, I'm ${this.name}`;
    }
    
    getAge() {
        return this.age;
    }
    
    // Getter
    get fullInfo() {
        return `${this.name}, ${this.age} years old`;
    }
    
    // Setter
    set age(newAge) {
        if (newAge > 0) {
            this._age = newAge;
        }
    }
    
    // Static method
    static compareAges(person1, person2) {
        return person1.age - person2.age;
    }
}

// Using the class
let john = new Person("John", 30);
console.log(john.greet()); // "Hello, I'm John"
console.log(john.fullInfo); // "John, 30 years old"
console.log(Person.compareAges(john, mary));
```

### Inheritance
```javascript
class Employee extends Person {
    constructor(name, age, jobTitle) {
        super(name, age); // Call parent constructor
        this.jobTitle = jobTitle;
    }
    
    // Override method
    greet() {
        return `${super.greet()}, I work as a ${this.jobTitle}`;
    }
    
    // New method
    work() {
        return `${this.name} is working as a ${this.jobTitle}`;
    }
}

let developer = new Employee("Alice", 28, "Developer");
console.log(developer.greet()); // "Hello, I'm Alice, I work as a Developer"
console.log(developer.work()); // "Alice is working as a Developer"
```

### Private Fields and Methods (ES2022)
```javascript
class BankAccount {
    #balance = 0; // Private field
    #accountNumber; // Private field
    
    constructor(accountNumber, initialBalance = 0) {
        this.#accountNumber = accountNumber;
        this.#balance = initialBalance;
    }
    
    // Private method
    #validateAmount(amount) {
        return amount > 0 && typeof amount === 'number';
    }
    
    // Public methods
    deposit(amount) {
        if (this.#validateAmount(amount)) {
            this.#balance += amount;
            return true;
        }
        return false;
    }
    
    withdraw(amount) {
        if (this.#validateAmount(amount) && this.#balance >= amount) {
            this.#balance -= amount;
            return true;
        }
        return false;
    }
    
    getBalance() {
        return this.#balance;
    }
}

let account = new BankAccount("12345", 1000);
account.deposit(500);
console.log(account.getBalance()); // 1500
// console.log(account.#balance); // Error! Private field
```

### Prototypes (Traditional OOP)
```javascript
// Constructor function
function Animal(name, species) {
    this.name = name;
    this.species = species;
}

// Add method to prototype
Animal.prototype.speak = function() {
    return `${this.name} makes a sound`;
};

Animal.prototype.getInfo = function() {
    return `${this.name} is a ${this.species}`;
};

// Create instances
let dog = new Animal("Buddy", "Dog");
console.log(dog.speak()); // "Buddy makes a sound"

// Inheritance with prototypes
function Dog(name, breed) {
    Animal.call(this, name, "Dog"); // Call parent constructor
    this.breed = breed;
}

// Set up inheritance
Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

// Override method
Dog.prototype.speak = function() {
    return `${this.name} barks`;
};

// Add new method
Dog.prototype.wagTail = function() {
    return `${this.name} wags tail`;
};

let myDog = new Dog("Max", "Golden Retriever");
console.log(myDog.speak()); // "Max barks"
console.log(myDog.getInfo()); // "Max is a Dog"
```

---

## Modules

### ES6 Modules

#### Exporting
```javascript
// math.js - Named exports
export function add(a, b) {
    return a + b;
}

export function multiply(a, b) {
    return a * b;
}

export const PI = 3.14159;

// Export all at once
function subtract(a, b) {
    return a - b;
}

function divide(a, b) {
    return a / b;
}

export { subtract, divide };

// Default export
export default function calculateArea(radius) {
    return PI * radius * radius;
}
```

#### Importing
```javascript
// Importing named exports
import { add, multiply, PI } from './math.js';

// Importing with alias
import { add as addition, multiply as multiplication } from './math.js';

// Import all named exports
import * as MathUtils from './math.js';
console.log(MathUtils.add(2, 3));

// Import default export
import calculateArea from './math.js';

// Import both default and named
import calculateArea, { add, PI } from './math.js';

// Dynamic imports
async function loadMath() {
    const mathModule = await import('./math.js');
    console.log(mathModule.add(2, 3));
}
```

### CommonJS (Node.js)
```javascript
// math.js - Exporting
function add(a, b) {
    return a + b;
}

function multiply(a, b) {
    return a * b;
}

module.exports = {
    add,
    multiply,
    PI: 3.14159
};

// Or single export
module.exports = function calculateArea(radius) {
    return 3.14159 * radius * radius;
};

// main.js - Importing
const { add, multiply, PI } = require('./math.js');
const math = require('./math.js');
```

---

## APIs and Fetch

### Fetch API
```javascript
// GET request
fetch('https://api.example.com/users')
    .then(response => {
        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }
        return response.json();
    })
    .then(data => {
        console.log('Users:', data);
    })
    .catch(error => {
        console.error('Error:', error);
    });

// With async/await
async function fetchUsers() {
    try {
        const response = await fetch('https://api.example.com/users');
        
        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }
        
        const data = await response.json();
        console.log('Users:', data);
        return data;
    } catch (error) {
        console.error('Error:', error);
        throw error;
    }
}
```

### POST Request
```javascript
// POST with JSON data
async function createUser(userData) {
    try {
        const response = await fetch('https://api.example.com/users', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
                'Authorization': 'Bearer ' + token
            },
            body: JSON.stringify(userData)
        });
        
        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }
        
        const data = await response.json();
        return data;
    } catch (error) {
        console.error('Error creating user:', error);
        throw error;
    }
}

// Usage
createUser({
    name: "John Doe",
    email: "john@example.com"
});
```

### Other HTTP Methods
```javascript
// PUT request
async function updateUser(id, userData) {
    const response = await fetch(`https://api.example.com/users/${id}`, {
        method: 'PUT',
        headers: {
            'Content-Type': 'application/json'
        },
        body: JSON.stringify(userData)
    });
    return response.json();
}

// DELETE request
async function deleteUser(id) {
    const response = await fetch(`https://api.example.com/users/${id}`, {
        method: 'DELETE'
    });
    return response.ok;
}

// PATCH request
async function partialUpdateUser(id, updates) {
    const response = await fetch(`https://api.example.com/users/${id}`, {
        method: 'PATCH',
        headers: {
            'Content-Type': 'application/json'
        },
        body: JSON.stringify(updates)
    });
    return response.json();
}
```

### Working with Different Response Types
```javascript
// JSON response
const jsonData = await response.json();

// Text response
const textData = await response.text();

// Blob for files
const blob = await response.blob();

// ArrayBuffer for binary data
const buffer = await response.arrayBuffer();

// FormData
const formData = await response.formData();

// Check response headers
console.log(response.headers.get('content-type'));
console.log(response.status);
console.log(response.statusText);
```

### Error Handling and Retry Logic
```javascript
async function fetchWithRetry(url, options = {}, retries = 3) {
    for (let i = 0; i < retries; i++) {
        try {
            const response = await fetch(url, options);
            
            if (response.ok) {
                return response;
            }
            
            // If it's the last retry or a client error, throw
            if (i === retries - 1 || response.status < 500) {
                throw new Error(`HTTP error! status: ${response.status}`);
            }
            
        } catch (error) {
            if (i === retries - 1) {
                throw error;
            }
            
            // Wait before retrying
            await new Promise(resolve => setTimeout(resolve, 1000 * (i + 1)));
        }
    }
}
```

---

## Best Practices

### 1. Use Strict Mode
```javascript
'use strict';

// This prevents common mistakes and makes debugging easier
```

### 2. Use Meaningful Variable Names
```javascript
// Good
let userAge = 25;
let isLoggedIn = true;
let calculateTotalPrice = (items) => { /* ... */ };

// Bad
let a = 25;
let flag = true;
let calc = (x) => { /* ... */ };
```

### 3. Use const and let Instead of var
```javascript
// Good
const PI = 3.14159;
let counter = 0;

// Bad
var PI = 3.14159;
var counter = 0;
```

### 4. Use Template Literals
```javascript
// Good
const message = `Hello, ${name}! You have ${count} new messages.`;

// Bad
const message = "Hello, " + name + "! You have " + count + " new messages.";
```

### 5. Use Arrow Functions Appropriately
```javascript
// Good for simple functions
const double = x => x * 2;
const sum = (a, b) => a + b;

// Use regular functions for methods that need 'this'
const obj = {
    name: "John",
    greet: function() {
        return `Hello, I'm ${this.name}`;
    }
};
```

### 6. Use Destructuring
```javascript
// Good
const { name, age, email } = user;
const [first, second] = array;

// Bad
const name = user.name;
const age = user.age;
const email = user.email;
```

### 7. Use Array Methods Instead of Loops
```javascript
// Good
const doubled = numbers.map(x => x * 2);
const evens = numbers.filter(x => x % 2 === 0);
const sum = numbers.reduce((acc, x) => acc + x, 0);

// Less preferred
const doubled = [];
for (let i = 0; i < numbers.length; i++) {
    doubled.push(numbers[i] * 2);
}
```

### 8. Handle Errors Properly
```javascript
// Good
async function fetchData() {
    try {
        const response = await fetch('/api/data');
        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }
        return await response.json();
    } catch (error) {
        console.error('Failed to fetch data:', error);
        throw error;
    }
}

// Bad
async function fetchData() {
    const response = await fetch('/api/data');
    return response.json(); // No error handling!
}
```

### 9. Use Consistent Code Style
```javascript
// Good - consistent formatting
const users = [
    { name: "John", age: 30 },
    { name: "Jane", age: 25 },
    { name: "Bob", age: 35 }
];

function processUsers(users) {
    return users
        .filter(user => user.age >= 30)
        .map(user => user.name)
        .sort();
}

// Bad - inconsistent formatting
const users=[{name:"John",age:30},{name:"Jane",age:25}];
function processUsers(users){
return users.filter(user=>user.age>=30).map(user=>user.name).sort();}
```

### 10. Comment Your Code
```javascript
/**
 * Calculates the compound interest
 * @param {number} principal - The initial amount
 * @param {number} rate - The interest rate (as decimal)
 * @param {number} time - Time period in years
 * @param {number} compoundFreq - How many times interest is compounded per year
 * @returns {number} The final amount after compound interest
 */
function calculateCompoundInterest(principal, rate, time, compoundFreq) {
    // Formula: A = P(1 + r/n)^(nt)
    return principal * Math.pow(1 + rate / compoundFreq, compoundFreq * time);
}
```

---

## Practice Exercises

### Exercise 1: Todo List App
Create a todo list application with:
- Add new tasks
- Mark tasks as complete
- Delete tasks
- Filter tasks (all, active, completed)
- Local storage persistence

### Exercise 2: Weather App
Build a weather application that:
- Fetches weather data from an API
- Displays current weather
- Shows 5-day forecast
- Handles loading states and errors
- Uses geolocation to get user's location

### Exercise 3: Calculator
Create a functional calculator with:
- Basic arithmetic operations
- Memory functions
- Keyboard support
- History of calculations
- Error handling for invalid operations

### Exercise 4: Image Gallery
Build an image gallery that:
- Displays thumbnails
- Modal view for full-size images
- Navigation between images
- Keyboard controls
- Lazy loading for performance

### Exercise 5: Shopping Cart
Create a shopping cart system with:
- Add/remove items
- Update quantities
- Calculate totals with tax
- Apply discount codes
- Form validation for checkout

---

## Quick Reference Cheat Sheet

### Variables and Types
```javascript
let variable = value;              // Mutable variable
const constant = value;            // Immutable variable
typeof variable                    // Check type
```

### Functions
```javascript
function name(params) { }          // Function declaration
const name = (params) => { };      // Arrow function
function name(param = default) { } // Default parameters
```

### Arrays
```javascript
arr.push(item)                     // Add to end
arr.pop()                          // Remove from end
arr.map(fn)                        // Transform each element
arr.filter(fn)                     // Select elements
arr.reduce(fn, initial)            // Combine elements
```

### Objects
```javascript
obj.property                       // Dot notation
obj["property"]                    // Bracket notation
Object.keys(obj)                   // Get all keys
Object.values(obj)                 // Get all values
```

### DOM
```javascript
document.querySelector(selector)   // Select element
element.addEventListener(event, fn) // Add event listener
element.innerHTML = html           // Set HTML content
element.style.property = value     // Set CSS style
```

### Async
```javascript
await promise                      // Wait for promise
fetch(url).then(response => ...)   // HTTP request
setTimeout(fn, ms)                 // Delay execution
```

---

## Resources for Further Learning

- [MDN JavaScript Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript) - Comprehensive JavaScript reference
- [JavaScript.info](https://javascript.info/) - Modern JavaScript tutorial
- [Eloquent JavaScript](https://eloquentjavascript.net/) - Free online book
- [You Don't Know JS](https://github.com/getify/You-Dont-Know-JS) - Deep dive book series
- [JS Fiddle](https://jsfiddle.net/) - Online JavaScript playground
- [CodePen](https://codepen.io/) - Frontend development playground
- [JavaScript30](https://javascript30.com/) - 30 day JavaScript challenge
- [FreeCodeCamp](https://www.freecodecamp.org/) - Free coding bootcamp
- [LeetCode](https://leetcode.com/) - Programming practice problems

---

**Remember**: JavaScript is a powerful and flexible language. Start with the basics, practice regularly, and gradually work your way up to more advanced concepts. Don't be afraid to experiment and make mistakes - that's how you learn!

Happy coding! 🎉
