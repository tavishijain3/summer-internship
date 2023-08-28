## JavaScript Quiz - Basic Level 4


### Theory:

#### **1. What are anonymous functions in JavaScript?**

Anonymous functions are functions without a name. They are often used as arguments to other functions or within expressions. An example is (function() { /* code */ })();.

#### **2. Explain strict comparison and Abstract comparison in javascript?**
Strict comparison (===): Checks for both value and type equality.
Abstract comparison (==): Performs type coercion, converting operands to the same type before comparison.

#### **3. Difference b/w arrow functions and regular functions?**

Arrow functions: Concise syntax, lexically bind this, no arguments object, cannot be used as constructors.
Regular functions: More flexible, have their own this and arguments, can be used as constructors.

#### **4. What is Hoisting in JavaScript?**

Hoisting is a behavior where variable and function declarations are moved to the top of their containing scope during compilation, allowing them to be used before they are declared.

#### **5. JavaScript is a garbage collected programming language, explain how?**

JavaScript's garbage collector automatically reclaims memory used by values that are no longer referenced by the program, ensuring efficient memory management.

#### **6. Explain Shallow copy vs Deep copy in Javascript?**

Shallow copy: Creates a new object, but nested objects are still referenced, not cloned.
Deep copy: Creates a completely independent copy of an object, including nested objects.

#### **7. What is Object.freeze?**

Object.freeze is a method that prevents changes to an object. It makes an object immutable by preventing adding, updating, or deleting properties and their attributes.

---
### Programs:

#### **1. Write a function that generates a random number between two ranges, -100 to 0 and 800 - 900.**
``` javascript
function randomInTwoRange(min1, max1, min2, max2) {
    const random1 = Math.random() * (max1 - min1) + min1;
    const random2 = Math.random() * (max2 - min2) + min2;

    return Math.random() < 0.5 ? random1 : random2;
}

const generatedNumbers = [];
for (let i = 0; i < 8; i++) {
    const randomNumber = randomInTwoRange(-100, 0, 800, 900);
    generatedNumbers.push(randomNumber);
}

console.log("Generated Numbers:", generatedNumbers);

```
---

