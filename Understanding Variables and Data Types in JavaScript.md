# Understanding Variables and Data Types in JavaScript

A **variable** is like a box with a label. You put a value inside the box, and later you can read it, change it, or use it in calculations.

*   Want to store a user’s name? Use a variable.
    
*   Want to track a score in a game? Use a variable.
    
*   Want to check if someone is logged in? Use a variable.
    

Without variables, your program would have no memory.

## 📦 Declaring Variables: `var`, `let`, and `const`

JavaScript gives you three keywords to create variables:

```javascript
var name = "Ashish";
let age = 25;
const country = "India";
```

Each one behaves slightly differently.

## 🧪 Primitive Data Types in JavaScript

Primitive data types are the simplest forms of data. They store single values.

*   **string** — text  
    `"Ashish"`, `"Hello"`, `"JavaScript"`
    
*   **number** — any number  
    `25`, `3.14`, `1000`
    
*   **boolean** — true/false  
    `true`, `false`
    
*   **null** — intentional “empty” value  
    `null`
    
*   **undefined** — variable declared but not assigned  
    `let x; // x is undefined`
    

### Simple examples

```javascript
let name = "Ashish";     // string
let age = 22;            // number
let isStudent = true;    // boolean
let middleName = null;   // null
let address;             // undefined
```

## 🔍 Basic Difference Between `var`, `let`, and `const`

| Keyword | Can Reassign? | Scope Type | Notes |
| --- | --- | --- | --- |
| **var** | Yes | Function scope | Old way, avoid in modern JS |
| **let** | Yes | Block scope | Best for values that change |
| **const** | No | Block scope | Best for fixed values |

### Example of changing values

```javascript
let score = 10;
score = 20; // works

const pi = 3.14;
pi = 3.15; // ❌ error: cannot reassign const
```

## 🌍 Understanding Scope (Beginner-Friendly)

**Scope** decides *where* a variable can be used.

Think of scope like rooms in a house:

*   A variable declared inside a room (block) is only usable in that room.
    
*   A variable declared outside is usable everywhere.
    

### Example

```javascript
{
  let x = 10;
  console.log(x); // works
}

console.log(x); // ❌ error: x is not defined
```

`x` only exists inside the `{ }` block.

## 🖼️ Simple Scope Visualization

```javascript
Global Scope
 ├── Accessible everywhere
 └── {
        Block Scope
        └── Accessible only inside this block
     }
```

## 📝 Example

### Task

Declare variables for:

*   Name
    
*   Age
    
*   IsStudent
    

Print them in the console.

### Starter Code

```javascript
let name = "Ashish";
let age = 22;
let isStudent = true;

console.log(name);
console.log(age);
console.log(isStudent);
```

### Try This

1.  Change the value of `name` and `age` — it should work.
    
2.  Change the value of a `const` variable — you should see an error.
    

## 📊 Diagram: var vs let vs const (Quick Comparison)

```javascript
+---------+----------------+----------------+
| Keyword | Reassignable?  | Scope          |
+---------+----------------+----------------+
| var     | Yes            | Function       |
| let     | Yes            | Block          |
| const   | No             | Block          |
+---------+----------------+----------------+
```
