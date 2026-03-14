# Control Flow in JavaScript: If, Else, and Switch Explained

Control flow in JavaScript is the system that decides **which code runs, when it runs, and under what conditions**. A simple way to think about it is: programming is full of decisions, just like real life. When you decide *“If it’s raining, take an umbrella; otherwise, go without it”*, you’re already using control flow logic.

## What Control Flow Means in Programming

Control flow is the **order in which statements are executed** in a program. By default, JavaScript runs code from **top to bottom**, but decision-making statements let you *change the path* based on conditions.

Real-life examples:

*   If you’re hungry → eat food
    
*   Else → continue working
    
*   If marks ≥ 90 → grade A
    
*   Else if marks ≥ 75 → grade B
    
*   Else → grade C
    

Programming uses the same logic.

## 🔍 The `if` Statement

The simplest decision-making tool.

It checks a condition, and **runs code only if the condition is true**.

### Example

```javascript
let age = 20;

if (age >= 18) {
  console.log("You are an adult.");
}
```

### Step-by-step

1.  JavaScript checks: `age >= 18`
    
2.  If true → prints “You are an adult.”
    
3.  If false → skips the block
    

## 🔄 The `if-else` Statement

Use this when you want **two possible outcomes**.

### Example

```javascript
let marks = 45;

if (marks >= 40) {
  console.log("Pass");
} else {
  console.log("Fail");
}
```

### How it flows

*   If condition is true → run first block
    
*   Else → run the second block
    

## 🪜 The `else if` Ladder

Use this when you have **multiple conditions** to check in sequence.

### Example

```javascript
let score = 82;

if (score >= 90) {
  console.log("Grade A");
} else if (score >= 75) {
  console.log("Grade B");
} else if (score >= 60) {
  console.log("Grade C");
} else {
  console.log("Grade D");
}
```

### Flow

JavaScript checks conditions **top to bottom** and stops at the first true one.

## 🔀 The `switch` Statement

`switch` is used when you want to compare **one value** against **multiple possible cases**.

### Example

```javascript
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
    console.log("Invalid day");
}
```

### Why `break` is important

Without `break`, JavaScript continues executing the next cases (called *fall-through*), which usually causes unwanted output.

## ⚖️ When to Use `switch` vs `if-else`

| Situation | Use |  |  |
| --- | --- | --- | --- |
| Many conditions based on **ranges** (age, marks, salary) | `if-else` |  |  |
| Many conditions based on **one fixed value** (day, month, menu option) | `switch` |  |  |
| Need cleaner, more readable branching | `switch` |  |  |
| Need complex logical expressions (`&&`, \` |  | \`) | `if-else` |

## 🧭 Flowchart: If-Else Decision Making

```javascript
        [Condition True?]
              /    \
            Yes     No
            /        \
   [Run If Block]   [Run Else Block]
```

## 🧩 Switch-Case Branching Diagram

```javascript
          [Value]
             |
   ---------------------
   |   |   |   |   |   |
 case1 case2 case3 ... default
   |     |     |        |
 [run] [run] [run]    [run]
   |     |     |        |
 break break break     end
```

## 📝 Assignment Ideas

### 1) Check if a number is positive, negative, or zero

**Why use if-else?**  
Because we are checking **ranges** (greater than, less than, equal to).

```javascript
let num = -5;

if (num > 0) {
  console.log("Positive");
} else if (num < 0) {
  console.log("Negative");
} else {
  console.log("Zero");
}
```

### 2) Print the day of the week using switch

**Why use switch?**  
Because we are comparing **one value** (`day`) with **fixed cases** (1–7).

```javascript
let day = 5;

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
  case 4:
    console.log("Thursday");
    break;
  case 5:
    console.log("Friday");
    break;
  case 6:
    console.log("Saturday");
    break;
  case 7:
    console.log("Sunday");
    break;
  default:
    console.log("Invalid day");
}
```
