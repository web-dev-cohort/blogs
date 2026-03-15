# JavaScript Arrays

## What Arrays Are and Why We Need Them

An array is a **collection of values stored in order**. Each value has a fixed position called an **index**, which helps you access it later.

A relatable example:

```javascript
// Without an array
let fruit1 = "Apple";
let fruit2 = "Banana";
let fruit3 = "Mango";

// With an array
let fruits = ["Apple", "Banana", "Mango"];
```

Arrays help when:

*   You have multiple related values
    
*   You want to loop through items
    
*   You want to update or access values easily
    

## How to Create an Array

JavaScript offers simple ways to create arrays.

### Using square brackets (most common)

```javascript
let fruits = ["Apple", "Banana", "Mango"];
```

### Creating an empty array

```javascript
let tasks = [];
```

## Accessing Elements Using Index

Array indexing starts from **0**, not 1.

| Index | Value |
| --- | --- |
| 0 | Apple |
| 1 | Banana |
| 2 | Mango |

Example:

```javascript
let fruits = ["Apple", "Banana", "Mango"];

console.log(fruits[0]); // Apple
console.log(fruits[2]); // Mango
```

## Updating Elements

You can replace any value by assigning a new one to its index.

```javascript
let marks = [85, 90, 78];

marks[1] = 95; // Update second value

console.log(marks); // [85, 95, 78]
```

## The Array Length Property

`length` tells you how many items are inside the array.

```javascript
let tasks = ["Study", "Exercise", "Cook"];

console.log(tasks.length); // 3
```

This is especially useful when looping.

## Basic Looping Over Arrays

Loops help you process each element one by one.

### Using a simple `for` loop

```javascript
let fruits = ["Apple", "Banana", "Mango"];

for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i]);
}
```

This prints:

```javascript
Apple
Banana
Mango
```

## Visual Diagram: Index and Values

Code

```javascript
Index:  0       1        2        3
Value: Apple   Banana   Mango   Orange
```

Think of it like labeled boxes in a row—each box has a number (index) and contains a value.
