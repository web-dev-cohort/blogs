# JavaScript Operators

JavaScript operators are the symbols that let you **perform actions** on values—like doing math, comparing numbers, checking conditions, or updating variables. Think of them as the small tools that make your code *do things*.

This article walks through the most common operators you’ll use every day, with simple examples, console outputs, and clear explanations.

## What Operators Are

Operators are symbols that tell JavaScript to perform an operation.  
Examples:

*   `+` adds numbers
    
*   `==` compares values
    
*   `&&` checks if two conditions are true
    

Every operator works with **operands** (the values around it):

```javascript
5 + 3
^   ^
|   |
operands
```

## ➕ Arithmetic Operators

These are the operators you already know from basic math.

| Operator | Meaning | Example | Result |
| --- | --- | --- | --- |
| `+` | Addition | `5 + 3` | `8` |
| `-` | Subtraction | `10 - 4` | `6` |
| `*` | Multiplication | `6 * 2` | `12` |
| `/` | Division | `20 / 5` | `4` |
| `%` | Remainder | `10 % 3` | `1` |

### Console Examples

```javascript
console.log(5 + 3);   // 8
console.log(10 - 4);  // 6
console.log(6 * 2);   // 12
console.log(20 / 5);  // 4
console.log(10 % 3);  // 1
```

## Comparison Operators

These operators compare two values and return **true** or **false**.

| Operator | Meaning | Example | Result |
| --- | --- | --- | --- |
| `==` | Equal (loose) | `5 == "5"` | true |
| `===` | Equal (strict) | `5 === "5"` | false |
| `!=` | Not equal | `10 != 5` | true |
| `>` | Greater than | `8 > 3` | true |
|  | Less than | `2 < 1` | false |

### The Important Difference: `==` vs `===`

*   `==` compares **values only**
    
*   `===` compares **values AND types**
    

```javascript
console.log(5 == "5");   // true  (same value)
console.log(5 === "5");  // false (different types)
```

Use `===` in real projects—it avoids unexpected results.

## Logical Operators

Logical operators help you combine conditions.

| Operator | Meaning | Example | Result |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- |
| `&&` | AND | `true && false` | false |  |  |  |  |
| \` |  | \` | OR | \`true |  | false\` | true |
| `!` | NOT | `!true` | false |  |  |  |  |

### Truth Table (Simplified)

| A | B | A && B | A \\|\\| B |  
|---|---|--------|----------|  
| true | true | true | true |  
| true | false | false | true |  
| false | true | false | true |  
| false | false | false | false |

### Console Examples

```javascript
console.log(true && false); // false
console.log(true || false); // true
console.log(!true);         // false
```

## Assignment Operators

These operators assign values to variables.

| Operator | Meaning | Example | Equivalent To |
| --- | --- | --- | --- |
| `=` | Assign | `x = 5` | — |
| `+=` | Add & assign | `x += 3` | `x = x + 3` |
| `-=` | Subtract & assign | `x -= 2` | `x = x - 2` |

### Console Example

```javascript
let x = 10;
x += 5;   // x = 15
x -= 3;   // x = 12
console.log(x); // 12
```

## 📊 Operator Categories (Quick Diagram)

```javascript
+----------------------+-----------------------------+
| Category             | Operators                   |
+----------------------+-----------------------------+
| Arithmetic           | +  -  *  /  %               |
| Comparison           | ==  ===  !=  >  <           |
| Logical              | &&  ||  !                   |
| Assignment           | =  +=  -=                   |
+----------------------+-----------------------------+
```

## Assignment for Practice

### 1\. Perform arithmetic on two numbers

```javascript
let a = 12;
let b = 5;

console.log(a + b);
console.log(a - b);
console.log(a * b);
console.log(a / b);
console.log(a % b);
```

### 2\. Compare values using `==` and `===`

```javascript
console.log(10 == "10");   // true
console.log(10 === "10");  // false
```

### 3\. Write a condition using logical operators

```javascript
let age = 20;
let hasID = true;

if (age >= 18 && hasID) {
  console.log("Allowed");
} else {
  console.log("Not allowed");
}
```

## Wrapping Up

Operators are the building blocks of logic and calculations in JavaScript. Once you understand arithmetic, comparison, logical, and assignment operators, you can start writing meaningful programs and conditions with confidence.
