## Typescript quiz (Basic Level - 1)

### Theory:

#### **1. What are the basic data types in TypeScript?**
In TypeScript, the basic data types include:
- **number**: Represents both integer and floating-point numbers.
- **string**: Represents a sequence of characters.
- **boolean**: Represents a true or false value.
- **null**: Represents an intentional absence of any object value.
- **undefined**: Represents an uninitialized variable.
- **object**: Represents a non-primitive value.
- **symbol**: Represents a unique and immutable value used as object property keys.
- **array**: Represents a collection of values of the same type.

#### **2. What is Generic data type?**
Generic data types allow you to create reusable components that work with multiple types, without specifying the actual type beforehand. They enable you to define functions, classes, or interfaces with placeholders for types, which are filled in when the component is used. This enhances code flexibility and reusability.

#### **3. What is type inferring in TS?**
Type inference in TypeScript refers to the compiler's ability to automatically deduce the data type of a value based on its context and assignment. This helps in writing cleaner code and reducing the need for explicit type annotations.

#### **4. What are the possible ways to define typing for functions?**
You can define typing for functions in TypeScript using these methods:
- **Explicit type annotations**: Specifying the parameter types and return type explicitly.
- **Type inference**: Allowing TypeScript to infer the types based on the function's implementation.
- **Interfaces and custom types**: Defining custom types or using interfaces to describe function shapes.

#### **5. How to define Generic type for Classes?**
You can define a generic type for classes in TypeScript by using angle brackets and a type parameter. 
For example:
```typescript
class MyClass<T> {
    private value: T;
    
    constructor(val: T) {
        this.value = val;
    }
    
    getValue(): T {
        return this.value;
    }
}
```

## Programs:

#### Type Definitions
```typescript
interface Todo {
    name: string;
    description: string;
    done: boolean;
}

type TodoList = Todo[];

type AddTodoFunction = (name: string, description: string) => number;
type RemoveTodoFunction = (index: number) => Todo[];
type ListTodosFunction = () => void;
type UpdateTodoFunction = (index: number, name: string, description: string) => Todo;
```

#### Functions
```typescript
const todos: TodoList = [];

const add: AddTodoFunction = (name, description) => {
    return todos.push({ name: name, description: description, done: false });
};

const remove: RemoveTodoFunction = (index) => {
    return todos.splice(index, 1);
};

const list: ListTodosFunction = () => {
    todos.forEach((todo, index) => {
        console.log(index + " - " + todo.name);
    });
};

const update: UpdateTodoFunction = (index, name, description) => {
    todos[index].name = name;
    todos[index].description = description;
    return todos[index];
};
```

## TYPESCRIPT TASK

### HTML (index.html)
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sequential Image Animation</title>
    <style>
        .image-container {
            display: flex;
            justify-content: space-around;
            margin-top: 50px;
        }
        img {
            width: 150px;
            height: 150px;
        }
    </style>
</head>
<body>
    <div class="image-container">
        <img id="image1" src="image1.jpg" alt="Image 1">
        <img id="image2" src="image2.jpg" alt="Image 2">
        <img id="image3" src="image3.jpg" alt="Image 3">
    </div>
    <script src="script.js"></script>
</body>
</html>
```

### JavaScript (script.js)
```javascript
const animation = [
    { transform: 'rotate(360deg) scale(1.2)' },
    { transform: 'rotate(0) scale(1)' }
];

const animationConfig = {
    duration: 2000,
    iterations: 1,
    fill: 'forwards'
};

const images = document.querySelectorAll(".image-container img");

function animateImage(image, animationConfig) {
    return new Promise((resolve) => {
        const animationPromise = image.animate(animation, animationConfig);
        animationPromise.finished.then(() => {
            resolve();
        });
    });
}

async function animateSequentially() {
    for (const image of images) {
        await animateImage(image, animationConfig);
    }
    console.log("All animations finished");
}

animateSequentially();
```

In this example, we have three images in the HTML file inside a flex container. The JavaScript code defines the animation properties, the animation configuration, and the functions to animate each image sequentially using Promises and the `animate` method. The `animateSequentially` function uses an async loop to wait for each animation to finish before proceeding to the next one.

---

