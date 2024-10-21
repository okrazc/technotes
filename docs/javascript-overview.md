---

# JavaScript Overview

JavaScript is a versatile scripting language that enables developers to create dynamic and interactive content for web pages. It works alongside HTML and CSS to make web applications more engaging by allowing users to interact with various elements on a webpage.

### 1. Variables in JavaScript
JavaScript variables are used to store data values. You declare variables using the `let` or `const` keywords:
- `let` is used for variables whose value can change over time.
- `const` is used for variables with values that remain constant after assignment.

Variables are dynamically typed, meaning their type is determined by the value assigned. For example:
```javascript
let number = 42; // number
const greeting = "Hello"; // string
```

### 2. Control Flow Statements
JavaScript provides several control flow statements to manage program execution:
- **If…Else Statements**: These are used for conditional execution of code.
- **Switch Statements**: Useful for executing code based on different possible values of an expression.
- **Loops**: JavaScript includes loops like `for`, `while`, and `do...while` for repeating blocks of code based on conditions.

Example of an `if…else` statement:
```javascript
if (x > 10) {
    console.log("x is greater than 10");
} else {
    console.log("x is 10 or less");
}
```

### 3. Functions in JavaScript
Functions are blocks of reusable code that can be called multiple times within a script. Functions in JavaScript can accept parameters and return values.

Example of a simple function:
```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
console.log(greet("Alice")); // Output: Hello, Alice!
```

### 4. Prototypes and Object Extensions
JavaScript objects can be extended with new properties and methods by modifying their prototypes. A prototype is a blueprint for an object that defines properties and methods that all instances of that object will inherit.

Example of adding a method to an object prototype:
```javascript
function Person(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
}

Person.prototype.getFullName = function() {
    return `${this.firstName} ${this.lastName}`;
};

const person1 = new Person("John", "Doe");
console.log(person1.getFullName()); // Output: John Doe
```

### 5. Client-Side Scripts
Client-side scripts are programs that run in the user’s browser alongside HTML documents. JavaScript is the most commonly used client-side scripting language, allowing developers to add interactivity and dynamic content to web pages, such as form validation, animations, and responsive elements.

### 6. The `<script>` Tag
JavaScript code can be embedded in HTML documents using the `<script>` tag. Scripts can either be written inline within the HTML document or loaded from external files.

Example of inline and external script usage:
```html
<!-- Inline script -->
<script>
  console.log("This script is running inline!");
</script>

<!-- External script -->
<script src="path/to/external/script.js"></script>
```

### 7. The Document Object Model (DOM)
The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the structure of a document as a tree of objects that can be manipulated with JavaScript. Using the DOM, JavaScript can interact with and modify HTML elements in real time.

### 8. Accessing DOM Elements
JavaScript can access and modify DOM elements using methods like `document.getElementById()` or `document.querySelector()`.

Example of accessing and modifying an element:
```javascript
const header = document.getElementById("header");
header.textContent = "Welcome to My Website!";
```

### 9. APIs for DOM Interaction
JavaScript APIs are often used to interact with the DOM. These APIs provide methods to manipulate elements, styles, events, and more. For example, the DOM API allows developers to update content, modify styles, and handle events such as clicks or form submissions.

Example of DOM manipulation via an API:
```javascript
const btn = document.querySelector(".my-button");
btn.addEventListener("click", () => {
    alert("Button clicked!");
});
```

---

Here’s an extended section for your JavaScript documentation page, covering the glossary terms you provided. You can incorporate this into your existing documentation on GitHub:

---

# JavaScript Glossary

This glossary provides definitions of key JavaScript terms to help clarify important concepts for both beginner and experienced developers.

### AJAX
**AJAX** (Asynchronous JavaScript and XML) is not a programming language but a programming concept that enables asynchronous server calls using JavaScript. It allows for the updating of web pages without reloading the entire page. While it originally used XML for data interchange, modern implementations typically use JSON (JavaScript Object Notation).

### Anonymous Functions
Anonymous functions are functions without a name. They are often used as arguments to other functions or for immediate execution after declaration. Anonymous functions are commonly utilized in situations where the function is not intended to be reused later.

### Array
An **array** is a data structure that stores multiple values in a single variable. Each value can be accessed using an index, starting from 0. Arrays are dynamic in JavaScript, allowing elements to be added or removed as needed.

### Classes
**Classes** act as templates for creating objects in JavaScript. They encapsulate data (properties) and functions (methods) to represent real-world entities and behaviors. Classes simplify the creation of multiple objects with similar attributes.

### Client-Side Script
A **client-side script** runs within the user’s browser, often in response to user interactions or page events. Scripts are embedded within HTML documents using the `<script>` tag and can be used for tasks like form validation or dynamic content updates.

### Document Objects
**Document objects** represent the main web page and give access to all the HTML elements on the page through JavaScript. When a web page loads, the HTML document becomes a "document" object, accessible via the `document` keyword.

### DOM (Document Object Model)
The **Document Object Model (DOM)** is an API that allows JavaScript to interact with and manipulate the structure, style, and content of a web page dynamically. It represents the page as a tree of objects, where each element on the page is a node in this tree.

### Element Nodes
**Element nodes** refer to the HTML tags within the DOM, such as `<div>`, `<p>`, or `<a>`. These nodes represent the structural elements of the document.

### Element Objects
**Element objects** are the most basic objects in the DOM, inheriting from a common base class. All HTML elements in a page are considered element objects, and they can be manipulated via JavaScript.

### Event
An **event** is an action or occurrence (like a mouse click or a keypress) that can be detected by JavaScript. JavaScript responds to events by executing a specific block of code.

### Event Binding
**Event binding** refers to associating an event (e.g., click, hover) with a JavaScript function. This tells the browser to execute the function when the specified event occurs.

### Event Handlers
**Event handlers** are functions that specify the actions to be performed when an event occurs. For example, you can use an event handler to display a message when a button is clicked:
```html
<button onclick="showAlert()">Click me</button>
<script>
function showAlert() {
    alert("Button clicked!");
}
</script>
```

### Extend
The **`extend`** keyword is used in class declarations to create a subclass (child class) that inherits properties and methods from another class (parent class).

### Functions
**Functions** are reusable blocks of code that perform specific tasks. They can accept arguments and return values. Functions are declared using the `function` keyword or arrow function syntax.

### IIFE (Immediately Invoked Function Expression)
An **IIFE** is a function that is executed immediately after it is defined. It is typically used to initialize variables or setup an environment without polluting the global scope.

Example:
```javascript
(function() {
    console.log("IIFE executed immediately");
})();
```

### Nodes
In the **DOM**, **nodes** are the building blocks of a document's structure, representing HTML elements, attributes, text, and other content.

### Objects
**Objects** are instances of classes that represent real-world entities. They contain properties (data) and methods (behaviors) that can be used to perform tasks and communicate with other components of a program.

### Prototypes
A **prototype** allows JavaScript objects to inherit properties and methods from a constructor function. By modifying the prototype, you can add new behaviors to all instances of an object created by the constructor.

Example:
```javascript
function Car(make, model) {
    this.make = make;
    this.model = model;
}
Car.prototype.getDetails = function() {
    return `${this.make} ${this.model}`;
};
```

### Script
A **script** in JavaScript can be embedded within an HTML document using the `<script>` tag. Scripts are used to add interactivity, perform form validation, and manipulate DOM elements dynamically.

### Self-Executing Functions
**Self-executing functions** are functions that run immediately upon definition. They are commonly used for initialization tasks and can be anonymous functions.

### Text Nodes
**Text nodes** are parts of the DOM that contain the actual text displayed between HTML element tags.

### `this`
The **`this`** keyword refers to the current instance of an object. Its value changes depending on the context in which it is used, making it an essential part of object-oriented programming in JavaScript.

---

