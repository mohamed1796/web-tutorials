## 1. Object Literal using JSON

Objects are created directly using JSON notation. Properties can be data or methods, and are accessed via dot or bracket notation.

```javascript
const person = {
  firstName: 'Sara',
  lastName: 'Ali',
  age: 25,
  getName() {
    return `${this.firstName} ${this.lastName}`;
  }
};

console.log(person.firstName);       // dot notation
console.log(person['age']);          // bracket notation
console.log(person.getName());       // method call
```

---

## 2. JSON.stringify & JSON.parse

JSON is used to serialize objects to strings (for storage/transport) and deserialize them back.

```javascript
const car = { brand: 'Toyota', year: 2022 };

const jsonString = JSON.stringify(car);   // object → string
console.log(jsonString);                  // {"brand":"Toyota","year":2022}

const carObject = JSON.parse(jsonString); // string → object
console.log(carObject.brand);            // Toyota
```

---

## 3. Object Destructuring

Extract object properties into variables concisely, including nested objects and rest syntax.

```javascript
const student = {
  firstname: 'Ali',
  lastname: 'Faleh',
  age: 18,
  address: { city: 'Doha', street: 'University St' }
};

const { firstname, age, address: { city }, ...rest } = student;
console.log(firstname); // Ali
console.log(city);      // Doha
console.log(rest);      // { lastname: 'Faleh' }
```

---

## 4. Class-based OOP

Classes define blueprints with constructors, getters, setters, and methods.

```javascript
class Person {
  constructor(firstname, lastname) {
    this.firstname = firstname;
    this.lastname = lastname;
  }

  get fullname() {
    return `${this.firstname} ${this.lastname}`;
  }

  set fullname(name) {
    [this.firstname, this.lastname] = name.split(' ');
  }

  greet() {
    return `Hello, my name is ${this.fullname}`;
  }
}

const p = new Person('Ahmed', 'Saleh');
console.log(p.greet()); // Hello, my name is Ahmed Saleh
p.fullname = 'Sara Nasser';
console.log(p.fullname); // Sara Nasser
```

---

## 5. Class Inheritance

A subclass extends a parent class using `extends` and calls the parent constructor with `super`.

```javascript
class Student extends Person {
  constructor(firstname, lastname, gpa) {
    super(firstname, lastname);
    this.gpa = gpa;
  }

  greet() {
    return `${super.greet()}. My GPA is ${this.gpa}`;
  }
}

const s = new Student('Ali', 'Faleh', 3.8);
console.log(s.greet()); // Hello, my name is Ali Faleh. My GPA is 3.8
```

---

## 6. Prototype Property

Methods and properties can be added to a class at runtime via `prototype`, affecting all instances.

```javascript
class Circle {
  constructor(r) { this.radius = r; }
}

Circle.prototype.getArea = function () {
  return Math.PI * this.radius ** 2;
};

const c = new Circle(5);
console.log(c.getArea().toFixed(2)); // 78.54
```

---

## 7. Private Attributes

Properties prefixed with `#` are private and only accessible inside the class.

```javascript
class BankAccount {
  #balance = 0;

  deposit(amount) { this.#balance += amount; }

  get balance() { return this.#balance; }
}

const acc = new BankAccount();
acc.deposit(500);
console.log(acc.balance); // 500
// console.log(acc.#balance); // SyntaxError
```

---

## 8. Static Properties & Methods

Static members belong to the class itself, not to any instance.

```javascript
class MathUtils {
  static PI = 3.14159;

  static circleArea(r) {
    return MathUtils.PI * r * r;
  }
}

console.log(MathUtils.PI);              // 3.14159
console.log(MathUtils.circleArea(4));   // 50.26...
```

---

## 9. Prototypal Inheritance

Objects can inherit directly from other objects using `Object.create()` or `Object.setPrototypeOf()`.

```javascript
const animal = { legs: 4, sound: 'generic' };

const dog = Object.create(animal);
dog.name = 'Rex';
dog.sound = 'Woof'; // shadows prototype value

console.log(dog.name);  // Rex  (own property)
console.log(dog.legs);  // 4    (inherited from animal)
console.log(dog.sound); // Woof (shadowed)
```

---

## 10. Prototype Chain

JavaScript resolves property lookups by walking up the chain of `__proto__` links until `null` is reached.

```javascript
const cat = { legs: 4, eyes: 2 };
const myCat = { name: 'Garfield', breed: 'Persian' };
Object.setPrototypeOf(myCat, cat);

console.log(myCat.name);                      // Garfield (own)
console.log(myCat.legs);                      // 4 (from cat)
console.log(myCat.hasOwnProperty('eyes'));    // false (from Object.prototype)
console.log(Object.getPrototypeOf(myCat) === cat); // true
```

---

## 11. Spread Operator for Cloning

The spread operator (`...`) clones an object and optionally overrides properties — no inheritance link.

```javascript
const movie1 = { title: 'Star Wars', episode: 7 };
const movie2 = { ...movie1, episode: 8, rating: 9 };

console.log(movie1.episode); // 7
console.log(movie2.episode); // 8
console.log(movie2.title);   // Star Wars
```

---

## 12. ES Modules (import / export)

Code can be split into reusable modules using named or default exports.

```javascript
// math.js — named exports
export const add = (x, y) => x + y;
export const multiply = (x, y) => x * y;

// app.js — named imports
import { add, multiply } from './math.js';
console.log(add(3, 4));       // 7
console.log(multiply(3, 4));  // 12
```

```javascript
// calculator.js — default export
class Calculator {
  add = (x, y) => x + y;
}
export default new Calculator();

// app.js — default import (any name allowed)
import calc from './calculator.js';
console.log(calc.add(5, 6)); // 11
```

---

## 13. NPM & Built-in Modules

Node.js offers built-in modules (`fs`, `path`) and NPM provides access to thousands of third-party packages.

```javascript
// Using built-in modules
import path from 'path';
import fs from 'fs';

const currentPath = path.resolve();
fs.readdir(currentPath, (err, files) => {
  files.forEach(file => console.log(file));
});
```

```bash
# NPM commands
npm init                  # initialize project
npm install lodash        # install a package
npm install mocha -D      # install dev dependency
npm install               # install all from package.json
```
