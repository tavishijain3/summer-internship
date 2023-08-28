## Javascript quiz (Basic Level - 1)

### Theory:

#### **1. What is JavaScript?**
JavaScript is a scripting or programming language that allows you to implement complex features on web pages — every time a web page does more than just sit there and display static information for you to look at — displaying timely content updates, interactive maps, animated 2D/3D graphics, scrolling video jukeboxes, etc. — you can bet that JavaScript is probably involved.

#### **2. What is the difference between b/w let and var?**
Variables declared by let are only available inside the block where they're defined. Variables declared by var are available throughout the function in which they're declared

#### **3. Why do we prefer const over var?**
var and let create variables that can be reassigned another value. const creates "constant" variables that cannot be reassigned another value. Developers shouldn't use var anymore, they should use let or const instead because if you're not going to change the value of a variable, it is good practice to use const.

#### **4. What is the use of javascript in web browsers?**
JavaScript enables you to create dynamically updating content, control multimedia, animate images, and pretty much everything else. Before JavaScript, web pages were built only with HTML and CSS. HTML and CSS are only capable of creating static pages that can be styled but not interactive aside from hyperlinks.

#### **5. What are Objects?**
An object is a collection of properties, and a property is an association between a name (or key) and a value. A property's value can be a function, in which case the property is known as a method.

#### **6. What is an array and how is it different from an Object in Javascript?**
We use arrays whenever we want to create and store a list of multiple items in a single variable. Arrays are especially useful when creating ordered collections where items in the collection can be accessed by their numerical position in the list. Objects represent “things” with characteristics (aka properties), while arrays create and store lists of data in a single variable.

#### **7. What is a function?**
A function in JavaScript is similar to a procedure—a set of statements that performs a task or calculates a value, but for a procedure to qualify as a function, it should take some input and return an output where there is some obvious relationship between the input and the output.

#### **8.How can we implement call by value and call by reference in Javascript?**
**Call by value:**
- Function arguments are always passed by value.
- It copies the value of a variable passed in a function to a local variable.
- Both these variables occupy separate locations in memory. Thus, if changes are made in a particular variable it does not affect the other one.
* **Example:-**
```// By value (primitives)
let a = 5;
let b;
b = a;
a = 3;
console.log(a);
console.log(b);
```
* #### **Output:-** 
             3
             5
Output “b” was just a copy of “a”. It has its own space in memory. When we change “a” it does not have any impact on the value of “b”. 

**Call by reference:**
- In JavaScript, all objects interact by reference.
- If an object is stored in a variable and that variable is made equal to another variable then both of them occupy the same location in memory.
- Changes in one object variable affect the other object variable.
* **Example:-**
```// By reference (all objects (including functions))
let c = { greeting: 'Welcome' };
let d;
d = c;
// Mutating the value of c
c.greeting = 'Welcome to geeksforgeeks';
console.log(c);
console.log(d);
```
* #### **Output:**
{greeting: 'Welcome to geeksforgeeks'}
{greeting: 'Welcome to geeksforgeeks'}by

#### **9. What are the primitive data types in Javascript?**
In JavaScript, a primitive (primitive value, primitive data type) is data that is not an object and has no methods or properties. There are 7 primitive data types:
#### a. string
#### b. number
#### c. bigint
#### d. boolean
#### e. undefined
#### f. symbol
#### g. null

#### **10. What is DOM?**
The Document Object Model (DOM) is a programming interface for web documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects; that way, programming languages can interact with the page.

#### **11. Why do we need DOM?**
HTML is used to structure the web pages and Javascript is used to add behavior to our web pages. When an HTML file is loaded into the browser, the javascript can not understand the HTML document directly. So, a corresponding document is created(DOM). DOM is basically the representation of the same HTML document but in a different format with the use of objects. Javascript interprets DOM easily i.e javascript can not understand the tags in HTML document but can understand object h1 in DOM. Now, Javascript can access each of the objects (h1, p, etc) by using different functions.
With DOM, we can easily access and manipulate tags, IDs, classes, Attributes, or Elements of HTML using commands or methods provided by the Document object. Using DOM, the JavaScript gets access to HTML as well as CSS of the web page and can also add behavior to the HTML elements.

## Programs

### 1. Average of array numbers in Javascript

```javascript
const nums = [10, 20, 30, 40, 50];

const total = nums.reduce((sum, num) => sum + num, 0);
const average = total / nums.length;

console.log(`Average: ${average}`);
```

### 2. Swap Two Numbers by Reference

```javascript
function swapByReference(a, b) {
    let temp = a;
    a = b;
    b = temp;
}

let num1 = 5;
let num2 = 10;

console.log(`Before swap: num1 = ${num1}, num2 = ${num2}`);
swapByReference(num1, num2);
console.log(`After swap: num1 = ${num1}, num2 = ${num2}`);
```

### 3. Print the Fibonacci Sequence

```javascript
function fibonacciSequence(n) {
    const sequence = [0, 1];

    for (let i = 2; i < n; i++) {
        const nextNum = sequence[i - 1] + sequence[i - 2];
        sequence.push(nextNum);
    }

    return sequence;
}

const n = 10;
const fibSequence = fibonacciSequence(n);
console.log(`Fibonacci Sequence (${n} terms): ${fibSequence.join(', ')}`);
```

### 4. Sort an Array by Ascending and Descending Order

```javascript
const numbers = [10, 5, 8, 2, 7];

const ascending = numbers.slice().sort((a, b) => a - b);
const descending = numbers.slice().sort((a, b) => b - a);

console.log('Original:', numbers);
console.log('Ascending:', ascending);
console.log('Descending:', descending);
```

### 5. Show a Variable Value in an HTML Webpage Using DOM

Assuming you have an HTML file with an element with the id "output":

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Variable Display</title>
</head>
<body>
    <p id="output">Variable value will be displayed here</p>
    <script src="script.js"></script>
</body>
</html>
```

Create a JavaScript file named "script.js" in the same directory as your HTML file:

```javascript
const variableValue = "Hello, World!"; // Change this value as needed

const outputElement = document.getElementById("output");
outputElement.textContent = variableValue;
```

---

## JavaScript Quiz - Basic Level 2

### Theory:

1. #### **Why do we use functions in JavaScript?**
   Functions in JavaScript are used to encapsulate and reuse blocks of code. They improve code organization, readability, and maintainability by allowing you to break down complex tasks into smaller, manageable parts.

2. #### **What is Function Invocation?**
   Function invocation refers to the process of calling a function in JavaScript. It involves providing arguments (if the function requires them) and executing the code within the function's body.

3. #### **Does a function behave like an object in JavaScript? Prove it by an example.**
   Yes, functions in JavaScript are first-class objects. They can be assigned to variables, passed as arguments, returned from other functions, and have properties and methods. For example:
   
   ```javascript
   function greet(name) {
       console.log(`Hello, ${name}!`);
   }

   greet.message = "Welcome!";
   greet("Alice");
   console.log(greet.message);
   ```

4. #### **What are Events in JavaScript?**
   Events in JavaScript are actions or occurrences that happen in the browser, such as a user clicking a button, a page finishing loading, or a mouse hovering over an element. JavaScript allows you to listen for and respond to these events, enabling dynamic interactions on web pages.

5. #### **What is a string?**
   A string is a sequence of characters (text) in JavaScript. It can include letters, numbers, symbols, and spaces.

6. #### **What is an array? Is it static or dynamic in JavaScript?**
   An array is a data structure that holds a collection of values, which can be of any data type. Arrays in JavaScript are dynamic, meaning you can add or remove elements from them after creation.

7. #### **Difference between Map and Set?**
   - `Map` allows you to store key-value pairs where keys can be any data type.
   - `Set` is a collection of unique values, where duplicate values are automatically removed.

8. #### **Difference between Array and Map?**
   - `Array` stores values at numeric indices.
   - `Map` stores key-value pairs where keys can be any data type.

9. #### **What are array methods? List a few names?**
   Array methods are built-in functions in JavaScript that allow you to perform various operations on arrays. Some examples include:
   - `push()`, `pop()`, `shift()`, `unshift()`
   - `concat()`, `slice()`, `splice()`
   - `forEach()`, `map()`, `filter()`, `reduce()`

10. #### **In how many ways can we traverse through an array in JavaScript?**
    You can traverse through an array in JavaScript using different methods:
    - Using a `for` loop
    - Using a `for...of` loop
    - Using the `forEach()` method
    - Using the `map()` method
    - Using the `filter()` method
    - Using the `reduce()` method

### Programs

1. **Reverse an Array**

```javascript
const inputArray = [1, 2, 3, 4, 5, 6];
const reversedArray = inputArray.reverse();

console.log(reversedArray);
```

2. **Explain the Properties of the `join` Array Method Function via Program**

```javascript
const fruits = ["apple", "banana", "orange"];
const joinedString = fruits.join(", "); // Joins array elements with a comma and space

console.log(joinedString); // Output: "apple, banana, orange"
```

3. **Show All the Values of an Array in an HTML Webpage Using DOM and `forEach` Method**

Assuming you have an HTML file with an element with the id "output":

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Array Values Display</title>
</head>
<body>
    <ul id="output"></ul>
    <script src="script.js"></script>
</body>
</html>
```

Create a JavaScript file named "script.js" in the same directory as your HTML file:

```javascript
const arrayValues = ["apple", "banana", "orange"];

const outputElement = document.getElementById("output");
arrayValues.forEach(value => {
    const listItem = document.createElement("li");
    listItem.textContent = value;
    outputElement.appendChild(listItem);
});
```

4. **Merge Two Sets in JavaScript Using the `Set` Class**

```javascript
const set1 = new Set([1, 2, 3]);
const set2 = new Set([3, 4, 5]);

const mergedSet = new Set([...set1, ...set2]);

console.log(mergedSet); // Output: Set { 1, 2, 3, 4, 5 }
```
---

