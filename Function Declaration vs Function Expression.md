# Function Declaration vs Function Expression: What’s the Difference?

A function is a **reusable block of code** designed to perform a specific task. Instead of repeating the same logic again and again, you wrap it inside a function and call it whenever needed.

Example: adding two numbers.

```javascript
function add(a, b) {
  return a + b;
}

console.log(add(3, 4)); // 7
```

Functions help you:

*   Avoid repeating code
    
*   Organize logic into meaningful units
    
*   Make programs easier to read and maintain
    

## Function Declaration Syntax

A **function declaration** defines a function using the `function` keyword at the top level.

```javascript
function greet(name) {
  return "Hello " + name;
}
```

Key points:

*   Has a name (`greet`)
    
*   Can be called **before or after** its definition (because of hoisting)
    
*   Commonly used for defining main reusable functions
    

## Function Expression Syntax

A **function expression** stores a function inside a variable.

```javascript
const greet = function(name) {
  return "Hello " + name;
};
```

You can also use arrow functions:

```javascript
const greet = (name) => "Hello " + name;
```

Key points:

*   Function is assigned to a variable
    
*   Cannot be called before the line where it is defined
    
*   Useful when passing functions as values (callbacks, event handlers)
    

## Key Differences Between Declaration and Expression

### Comparison Table

| Feature | Function Declaration | Function Expression |
| --- | --- | --- |
| Syntax | `function add() {}` | `const add = function() {}` |
| Hoisting | Fully hoisted (can call before definition) | Not hoisted in usable form |
| Name | Must have a name | Can be named or anonymous |
| When it’s created | At compile time | At runtime (when execution reaches it) |
| Common use | General-purpose functions | Callbacks, inline logic, arrow functions |

## Basic Idea of Hoisting (Very High Level)

Hoisting means JavaScript moves certain things to the top of the file **before** running the code.

*   **Function declarations** are hoisted completely → you can call them before they appear.
    
*   **Function expressions** are *not* hoisted as functions → only the variable is hoisted, not the function value.
    

Example:

```javascript
sayHello(); // Works

function sayHello() {
  console.log("Hello!");
}
```

But:

```javascript
sayHello(); // ❌ Error: sayHello is not a function

const sayHello = function() {
  console.log("Hello!");
};
```

## When to Use Each Type

### Use **Function Declarations** when:

*   You want the function available anywhere in the file
    
*   You’re defining main utilities or core logic
    
*   You prefer traditional, readable structure
    

### Use **Function Expressions** when:

*   You need a function as a value (callbacks, event handlers)
    
*   You want to use arrow functions
    
*   You want more control over when the function becomes available
    
*   You prefer block-scoped behavior with `const` or `let`
    

## Simple Side-by-Side Example

### Function Declaration

```javascript
function multiply(a, b) {
  return a * b;
}
```

### Function Expression

```javascript
const multiply = function(a, b) {
  return a * b;
};
```

Both work the same when called:

```javascript
console.log(multiply(3, 5)); // 15
```
