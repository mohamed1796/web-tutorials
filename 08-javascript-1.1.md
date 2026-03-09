# JavaScript Fundamentals Summary

This PDF provides a comprehensive introduction to JavaScript, covering core concepts from basic syntax to functional programming patterns. Here's a summary with code examples:

## 1. Introduction to JavaScript

JavaScript is a platform-independent scripting language used for client-side dynamic behavior and server-side applications (Node.js).

```javascript
// JavaScript can be embedded in HTML and run in browsers
console.log("Hello, JavaScript!");
```

## 2. Variable Declaration

Use `const` for immutable values and `let` for mutable variables.

```javascript
const height = 110; // Cannot be reassigned
let count = 5; // Can be reassigned
count = 10; // Valid
```

## 3. Data Types

JavaScript is loosely typed with 7 primitive types: number, bigint, string, boolean, undefined, function, and object.

```javascript
const count = 5; // number
const name = 'Ali Dahak'; // string
const isActive = true; // boolean
```

## 4. Template Literals

Create dynamic strings with embedded expressions.

```javascript
const person = {fname: 'Samir', lname: 'Mujtahid'};
console.log(`Full name: ${person.fname} ${person.lname}`);
// Output: "Full name: Samir Mujtahid"
```

## 5. Operators

JavaScript supports arithmetic, logical, comparison, and assignment operators.

```javascript
const a = 5;
const b = 4;
console.log(a >= b); // true
console.log(a === b); // false (strict equality)
console.log(0 == ""); // true (type coercion)
console.log(0 === ""); // false (no type coercion)
```

## 6. Conditional Statements

```javascript
const number = 10;
if (number % 2 === 0) {
    console.log('This number is even');
} else {
    console.log('This number is odd');
}
```

## 7. Loops

```javascript
// While loop
let counter = 0;
while (counter < 10) {
    console.log(`Number: ${counter}`);
    counter++;
}

// For loop
for (let i = 1; i <= n; i++) {
    factorial *= i;
}

// For-of loop
const nums = [1, 2, 3, 4, 5];
for (const n of nums) {
    sum += n;
}
```

## 8. Functions

```javascript
// Traditional function
function double(number) {
    return number * 2;
}

// Arrow function (Lambda)
const average = (a, b) => (a + b) / 2;
console.log(average(10, 20)); // 15
```

## 9. Arrays

```javascript
// Array declaration
const numbers = [1, 2, 3, 4, 5];

// Dynamic operations
numbers.push(6); // Add to end
numbers.pop(); // Remove from end
numbers.unshift(0); // Add to beginning
numbers.shift(); // Remove from beginning
```

## 10. Destructuring Assignment

```javascript
const colors = ["red", "green", "blue", "yellow"];
const [primaryColor, secondaryColor, ...otherColors] = colors;
// primaryColor = 'red'
// secondaryColor = 'green'
// otherColors = ['blue', 'yellow']
```

## 11. Spread Operator

```javascript
const nums = [5, 4, 23, 2];
const max = Math.max(...nums); // Convert array to arguments

const cold = ['autumn', 'winter'];
const warm = ['spring', 'summer'];
const seasons = [...cold, ...warm]; // Concatenate arrays
```

## 12. Array Methods with Lambda Functions

### Filter
```javascript
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9];
const evens = numbers.filter(n => n % 2 === 0);
// [2, 4, 6, 8]
```

### Map
```javascript
const squares = numbers.map(n => n ** 2);
// [1, 4, 9, 16, 25, 36, 49, 64, 81]
```

### Reduce
```javascript
const total = numbers.reduce((sum, n) => sum + n);
// 45
```

### Chaining Operations
```javascript
const result = numbers
    .filter(n => n % 2 === 0)  // Get even numbers
    .map(n => n ** 2)           // Square them
    .reduce((sum, n) => sum + n); // Sum them up
// 120
```

## 13. Find and FindIndex

```javascript
const numbers = [1, 2, 3, 4, 5];
const firstEven = numbers.find(n => n % 2 === 0);
// 2
```

## 14. Flat and FlatMap

```javascript
// Flatten nested arrays
const flattened = [['a', 'b', 'c'], ['d', 'e']].flat();
// ['a', 'b', 'c', 'd', 'e']

// Map then flatten
const books = [
    {title: "Book 1", authors: ["Author A", "Author B"]},
    {title: "Book 2", authors: ["Author C"]}
];
const authors = books.flatMap(b => b.authors);
// ["Author A", "Author B", "Author C"]
```

## 15. Rest Operator

```javascript
function sum(...args) {
    return args.reduce((prev, curr) => prev + curr);
}
console.log(sum(1, 3, 5)); // 9
```

## 16. Sets and Maps

```javascript
// Set (unique values)
const names = new Set();
names.add('Samir');
names.add('Fatima');
names.add('Samir'); // Won't be added (duplicate)

// Map (key-value pairs)
const map = new Map();
map.set(1, 'One');
map.set(2, 'Two');
console.log(map.get(1)); // 'One'
```

This summary covers the essential JavaScript concepts from the PDF with practical code examples for each topic.
