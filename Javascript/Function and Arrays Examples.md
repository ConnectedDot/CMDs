# Chapter 6: Functions and Arrays — Complete Templates & Examples

## 1. Using Functions

```javascript
// Basic function
function greet(name) {
    return `Hello, ${name}!`;
}
console.log(greet('Alice'));

// Functions as Values
const square = function(x) { return x * x; };
console.log(square(4));

// Function with default parameters
function introduce(name='Guest', age=0) {
    return `${name} is ${age} years old.`;
}
console.log(introduce()); // Guest, 0
console.log(introduce('Bob', 30));
```

## 2. Passing Functions as Arguments

```javascript
function processNumber(func, num) {
    return func(num);
}
console.log(processNumber(Math.sqrt, 16)); // 4

// Using anonymous functions
console.log(processNumber(function(n) { return n + 10; }, 5)); // 15
```

## 3. `Object.defineProperty()` & `Object.defineProperties()`

```javascript
let person = {};

Object.defineProperty(person, 'name', {
    value: 'Alice',
    writable: false,
    enumerable: true,
    configurable: false
});

console.log(person.name); // Alice
person.name = 'Bob'; // ignored due to writable:false
console.log(person.name); // Alice

// Multiple properties
Object.defineProperties(person, {
    age: {
        value: 25,
        writable: true
    },
    country: {
        value: 'USA',
        enumerable: true
    }
});
```

## 4. `Object.create()`

```javascript
const proto = {
    greet() { return 'Hi!'; }
};
const obj = Object.create(proto);
console.log(obj.greet()); // Hi!
```

## 5. Constructor Function with `new`

```javascript
function Person(name) {
    this.name = name;
}
const p1 = new Person('Alice');
console.log(p1.name); // Alice
```

## 6. Lazy Loading with Dynamic Import

```javascript
async function loadModule() {
    const module = await import('./someModule.js');
    module.doTask();
}
loadModule();
// (Note: Adjust path as needed.)
```

## 7. Recursion Example

```javascript
function factorial(n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}
console.log(factorial(5)); // 120
```

## 8. Borrowing Methods with `apply()` & `call()`

```javascript
const obj = { value: 42 };
function showValue() {
    console.log(this.value);
}

showValue.call(obj); // 42
showValue.apply(obj); // 42
```

## 9. Overriding `toString()`

```javascript
const obj = {
    id: 123,
    toString() {
        return `Object ID: ${this.id}`;
    }
};
console.log(obj.toString()); // Object ID: 123
```

## 10. Testing if Array

```javascript
console.log(Array.isArray([1, 2, 3])); // true
console.log([1,2,3] instanceof Array); // true
```

## 11. Clone Object Properties

```javascript
function cloneMembers(obj) {
    return Object.assign({}, obj);
}
const original = { a: 1, b: 2 };
const clone = cloneMembers(original);
console.log(clone); // { a: 1, b: 2 }
```

## 12. Currying Example

```javascript
function multiply(a) {
    return function(b) {
        return a * b;
    };
}
const double = multiply(2);
console.log(double(5)); // 10
```

## 13. Method Chaining

```javascript
const chainableObject = {
    value: 0,
    add(x) {
        this.value += x;
        return this;
    },
    subtract(x) {
        this.value -= x;
        return this;
    },
    getResult() {
        return this.value;
    }
};

console.log(
    chainableObject.add(5).subtract(2).add(10).getResult()
); // 13
```

## 14. Closures & Returning Functions

```javascript
function makeCounter() {
    let count = 0; // private variable
    return {
        increment() { count++; },
        getCount() { return count; }
    };
}

const counter = makeCounter();
counter.increment();
console.log(counter.getCount()); // 1
```

## 15. Passing Config Object

```javascript
function initSettings({ theme='light', language='en' } = {}) {
    console.log(`Theme: ${theme}, Language: ${language}`);
}

initSettings({ theme: 'dark' }); // Theme: dark, Language: en
initSettings(); // Theme: light, Language: en
```

## 16. Callback Functions & Asynchronous Example

```javascript
function fetchData(callback) {
    setTimeout(() => {
        callback('Data loaded');
    }, 1000);
}

fetchData(msg => console.log(msg)); // after 1s: Data loaded
```

## 17. Memoization Example

```javascript
function factorial(n, cache = {}) {
    if (n <= 1) return 1;
    if (cache[n]) return cache[n];
    cache[n] = n * factorial(n - 1, cache);
    return cache[n];
}

console.log(factorial(10)); // 3628800
```

---

## Further Practice Ideas

- Create a calculator object with chainable methods.
- Write a recursive Fibonacci generator with memoization.
- Implement an object that overrides `toString()` dynamically.
- Build a configurable module loader with lazy loading.
- Write a currying function that sums multiple arguments.

