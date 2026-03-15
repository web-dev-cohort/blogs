# Understanding Object-Oriented Programming in JavaScript
OOP is a programming style where you build software using **objects**—bundles of related data (properties) and actions (methods). Instead of writing scattered functions and variables, you group them into meaningful units.

This helps you:

*   Model real-world things (Car, Student, Person)
    
*   Reuse code efficiently
    
*   Keep logic organized and modular
    

## Real‑World Analogy: Blueprint → Objects

Think of a **Car blueprint**.  
A blueprint is *not* a car—it’s a **design** that describes what every car should have (color, model, engine) and what it can do (start, stop, accelerate).

From this blueprint, you can create many **car objects**:

*   Car 1: Red Honda
    
*   Car 2: Blue Toyota
    
*   Car 3: Black BMW
    

Each car is an **instance** of the blueprint.

In JavaScript:

*   The **blueprint** is a *class*
    
*   The **cars** are *objects created from the class*
    

## What Is a Class in JavaScript?

A **class** is a template for creating objects.  
It defines:

*   What properties the object will have
    
*   What methods (functions) the object can perform
    

Example: A simple `Car` class

```javascript
class Car {
  constructor(brand, color) {
    this.brand = brand;
    this.color = color;
  }

  start() {
    console.log(`${this.brand} is starting...`);
  }
}
```

## Creating Objects Using Classes

Once you define a class, you can create objects (instances) from it using the `new` keyword.

```javascript
const car1 = new Car("Honda", "Red");
const car2 = new Car("Toyota", "Blue");

car1.start(); // Honda is starting...
car2.start(); // Toyota is starting...
```

Each object has its own data but shares the same structure and behavior.

## The Constructor Method

The **constructor** is a special method inside a class.  
It runs automatically when you create a new object.

Purpose:

*   Initialize object properties
    
*   Set default values
    

Example:

```javascript
constructor(name, age) {
  this.name = name;
  this.age = age;
}
```

## Methods Inside a Class

Methods define what actions an object can perform.

Example:

```javascript
class Person {
  constructor(name) {
    this.name = name;
  }

  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
}

const p = new Person("Ashish");
p.greet(); // Hello, my name is Ashish
```

## Basic Idea of Encapsulation

Encapsulation means **bundling data and methods together** and controlling access to them.

Why it matters:

*   Prevents accidental modification
    
*   Keeps internal details hidden
    
*   Makes code safer and cleaner
    

JavaScript supports encapsulation using:

*   Public fields (`this.name`)
    
*   Private fields (`#salary`)
    

Example:

```javascript
class Employee {
  #salary; // private

  constructor(name, salary) {
    this.name = name;
    this.#salary = salary;
  }

  getSalary() {
    return this.#salary;
  }
}
```

## Assignment: Build Your Own `Student` Class

Try this exercise to strengthen your understanding.

### Task

1.  Create a class called `Student`
    
2.  Add properties: `name`, `age`
    
3.  Add a method `printDetails()`
    
4.  Create multiple student objects
    

### Sample Solution

```javascript
class Student {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }

  printDetails() {
    console.log(`Name: ${this.name}, Age: ${this.age}`);
  }
}

const s1 = new Student("Ashish", 22);
const s2 = new Student("Riya", 20);

s1.printDetails();
s2.printDetails();
```

## Diagram Ideas (Text‑Based Visuals)

### Blueprint → Object

```javascript
   CLASS (Blueprint)
   -----------------
   |  Car          |
   |  brand        |
   |  color        |
   |  start()      |
   -----------------

        ↓  create objects

   OBJECTS (Instances)
   -------------------------
   | car1: brand=Honda      |
   |        color=Red       |
   -------------------------
   | car2: brand=Toyota     |
   |        color=Blue      |
   -------------------------
```

### Class → Instance Relationship

```javascript
        Car (class)
           ↑
           |
   -----------------
   | new Car()     |
   -----------------
           |
   -----------------
   | car1 object   |
   -----------------
```
