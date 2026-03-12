# What Arrow Functions Are
Arrow functions are a concise syntax for writing functions introduced in ES6. They let you write the same logic with fewer characters and a more readable structure.

A normal function:

```javascript
function add(a, b) {
  return a + b;
}
```

Arrow function version:

```javascript
const add = (a, b) => a + b;
```

The logic is identical, but the arrow function is shorter and easier to scan.

## ✏️ Basic Arrow Function Syntax

The general structure is:

```javascript
const functionName = (parameters) => {
  // function body
};
```

Key points:

*   You store the function in a variable.
    
*   The `=>` arrow replaces the `function` keyword.
    
*   You can return values explicitly or implicitly.
    

## 👤 Arrow Functions with One Parameter

When there is **one parameter**, parentheses are optional.

Normal function:

```javascript
function square(n) {
  return n * n;
}
```

Arrow function:

```javascript
const square = n => n * n;
```

Before → After:

*   Before: `function square(n) { return n * n }`
    
*   After: `n => n * n`
    

## 👥 Arrow Functions with Multiple Parameters

With two or more parameters, parentheses are required.

Normal function:

```javascript
function multiply(a, b) {
  return a * b;
}
```

Arrow function:

```javascript
const multiply = (a, b) => a * b;
```

## 🎯 Implicit Return vs Explicit Return

### **Implicit Return**

If the function body is a single expression, you can skip `{}` and `return`.

```javascript
const greet = name => `Hello, ${name}!`;
```

This automatically returns the string.

### **Explicit Return**

Use `{}` when you need multiple statements.

js

```javascript
const greet = name => {
  const message = `Hello, ${name}!`;
  return message;
};
```

Rule of thumb:

*   **One-line logic → implicit return**
    
*   **Multi-step logic → explicit return**
    

## 🔍 Arrow Functions vs Normal Functions (Basic Differences)

| Feature | Normal Function | Arrow Function |
| --- | --- | --- |
| Syntax | Longer | Shorter, cleaner |
| `this` binding | Dynamic (`this` changes based on caller) | Lexical (`this` comes from surrounding scope) |
| Suitable for methods | Yes | Usually no |
| Best use cases | Object methods, constructors | Callbacks, array methods, small utilities |

For beginners, the most important difference is **shorter syntax** and **implicit return**. Deep `this` behavior can be learned later.

## 🔄 Normal Function → Arrow Function Transformation (Diagram Idea)

```javascript
function add(a, b) {
  return a + b;
}

        ↓

const add = (a, b) => a + b;
```

## 🧩 Arrow Function Syntax Breakdown (Diagram Idea)

```javascript
const add = (a, b) => a + b
      │       │       │
   variable   params  return value
```

## 📝 Assignment

### 1\. Write a normal function to calculate the square of a number

```javascript
function square(n) {
  return n * n;
}
```

### 2\. Rewrite it using an arrow function

```javascript
const square = n => n * n;
```

### 3\. Create an arrow function that returns whether a number is even or odd

```javascript
const isEven = num => (num % 2 === 0 ? "Even" : "Odd");
```

### 4\. Use an arrow function inside `map()` on an array

```javascript
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(n => n * 2);

console.log(doubled); // [2, 4, 6, 8, 10]
```

Arrow functions are one of the simplest upgrades you can make to your JavaScript style. They reduce clutter, improve readability, and fit perfectly with modern ES6+ code.
