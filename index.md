# 📘 JavaScript Course Notes  

These notes are a structured collection of **JavaScript fundamentals to advanced concepts**.  
They include explanations, syntax, and practical examples with code snippets for quick reference.  

## 🚀 Why JavaScript?  
- JavaScript is the **most popular programming language** for web development.  
- Runs in every modern browser (client-side).  
- Can also be used for **server-side development** (Node.js).  
- Essential for building **interactive and dynamic web applications**.  

## 🛠 Topics Covered  
- Variables & Constants  
- Functions & Scope  
- Arrays & Objects  
- DOM Manipulation  
- Events & Event Listeners  
- Loops & Conditions  
- String & Math Methods  
- ES6+ Features (let, const, arrow functions, template literals, etc.)  
- Async JavaScript (Promises, Async/Await, Fetch API)  
- Projects (Length Converter, FD Calculator, ToDo List, Snake Game, etc.)  

---

✨ Use these notes as a **study guide** while practicing JavaScript.



### Console Output  
```javascript
// logs message to console
console.log('Hello');
console.log('Happy New Year');
````

### Alert Box

```javascript
// creates alert box
alert("Hi");
```

### Variables

```javascript
let score = 0;   // initialization
score = 100;     // assignment
console.log("score is " + score); // logs the value in score

// dynamically typed
score = 10.5;
score = 'no score';

// constant
const pi = 3.14;
```

---

## 🔹 DOM Example – Length Converter

### HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <title>Length Converter</title>
</head>
<body>
  <div id="wrapper">
    <h2>cm to inches</h2>
    <div class="inputdiv">
      <input type="text" id="input" placeholder="length in cm">
    </div>
    <div>
      <button type="submit" onclick="convert()">Convert to inches</button>
    </div>
    <div id="result"></div>
  </div>

  <script>
    function convert(){
      const cmVal = Number(document.getElementById("input").value);
      const inchVal = cmVal / 2.54;
      const result = document.getElementById("result");
      result.innerHTML = inchVal.toFixed(3) + " inches";
    }
  </script>
</body>
</html>
```

### CSS

```css
html, body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
  background-color: #f5e8ba;
}

#wrapper div, #wrapper h2 {
  display: flex;
  justify-content: center;
}

h2 {
  color: #ffeba7;
  letter-spacing: 1px;
}

input {
  border-radius: 5px;
  border: 2px solid black;
  margin-top: 30px;
  height: 2em;
  width: 250px;
  padding-left: 10px;
}

input:active {
  border: none;
}

#wrapper {
  height: 500px;
  width: 400px;
  margin: 200px auto;
  background-color: #1f2029;
  border-radius: 10px;
  padding: 30px;
}

button {
  margin-top: 20px;
  background-color: #ffeba7;
  border-radius: 4px;
  height: 44px;
  font-weight: 600;
  padding: 0 30px;
  letter-spacing: 1px;
  border: none;
  color: #102770;
}

button:hover {
  cursor: pointer;
}

#result {
  color: white;
  margin-top: 20px;
  font-size: 32px;
}
```

---

## 🔹 User Input

```javascript
let name = prompt("What's your name?");
console.log('Hi', name);

let tickets = prompt('How many tickets do you want?');
console.log("You should pay ", Number(tickets) * 20);

let a = prompt("Enter a number");
console.log(Number(a) + 10);
```

---

## 🔹 Math Functions

```javascript
// rounding
Math.round(5.8); // 6
Math.round(5.1); // 5

// floor gives previous number
Math.floor(5.8); // 5

// ceil gives next number
Math.ceil(5.1); // 6

// square root
Math.sqrt(55); // 7.416...

// absolute value
Math.abs(-9); // 9

// power
Math.pow(8,5); // 32768

// min value
Math.min(8,5,7,8); // 5

// random between 0 and 1
Math.random();

// dice roll (1-6)
Math.floor(Math.random() * 6) + 1;

// random number (1-100)
Math.floor(Math.random() * 100) + 1;

// constants
Math.PI;
Math.E;
```

---

## 🔹 String and Template Literals  

### String Operations  
```javascript
let str1 = "Strive not to be a success, ";
let str2 = "but rather to be a value";

// joining strings
str1 + str2;
str1.concat(str2); // joins the two strings
````

### Partitioning String

```javascript
slice(start, end)
substring(start, end)
substr(start, length)

str2.slice(4,10);     // 'rather'
str2.slice(4);        // 'rather to be a value'
str2.slice(-5);       // 'value'

str2.substring(4,10); // 'rather'
str2.substr(4,10);    // 'rather to '
```

### Replace & Case Conversion

```javascript
str1.replace('Strive','Aim'); // 'Aim not to be a success, '
str1.toUpperCase();           // 'STRIVE NOT TO BE A SUCCESS, '
str1.toLowerCase();           // 'strive not to be a success, '
str1.length;                  // 28
```

### Trimming

```javascript
let str1 = "  Strive not to be a success, ";
str1.trim();       // "Strive not to be a success,"
str1.trimStart();  // "Strive not to be a success, "
str1.trimEnd();    // "  Strive not to be a success,"
```

### Padding

```javascript
let bill = 'Rs.10';
bill.padEnd(7,'0'); // 'Rs.1000'
```

### Character Access

```javascript
str1[1];          // 't'
str1.charAt(1);   // 't'
str1.charCodeAt(1); // 116
```

### Searching

```javascript
str1.indexOf('e');      // 5
str1.lastIndexOf('e');  // 23
str1.indexOf('z');      // -1

str1.search('not');     // 7
str1.search('nott');    // -1

str1.includes('not');   // true
str1.startsWith('S');   // true
```

---

### Template Literals (ES6)

```javascript
let firstName = "Ramya";
let lastName = "Murali";
let city = "Chennai";

// old way
console.log(firstName + " " + lastName + " lives in " + city);

// string interpolation
console.log(`${firstName} ${lastName} lives in ${city}`);

// multiline string
let msg = `happy
birthday`;
console.log(msg);

// quotes inside string
msg = "cat's name is toto";
msg = `cat's name is "toto"`;
```

---

## 🔹 Arrays

### Basics

```javascript
let num = 10;
let name = "vidhya";

let cities = ["Chennai", "Madurai", "Trichy"];
let marks = [78, 56, 67, 54, 98];

console.log(marks.length);       // total elements
console.log(cities[1]);          // access 2nd element
console.log(cities[3]);          // access 4th element
console.log(marks[marks.length - 1]); // last element
```

### Nested Arrays

```javascript
let arr = [5, 6, 7, "a", "abc", [3, 4]];
console.log(arr[5][1]); // 4

let matrix = [
  [3, 4, 5],
  [4, 5, 7],
  [6, 7, 8],
];
console.log(matrix[2][1]); // 7
```

### Array Methods

```javascript
let array = ["a", "b", "c", "d", "e"];

// push - add element to end
array.push("f");
console.log(array);

// pop - remove last element
console.log(array.pop());

// shift - remove first element
console.log(array.shift());
console.log(array);

// unshift - add element to start
console.log(array.unshift("a"));
console.log(array);

// splice - add/remove/replace elements
array.splice(2, 2);        // delete 2 elements at index 2
array.splice(1, 1, "m");   // replace element at index 1 with "m"
array.splice(1, 2, "x","y"); // replace 2 elements with "x" and "y"
array.splice(1, 0, "b");   // insert "b" at index 1
console.log(array);

// slice - extract portion
console.log(array.slice(1, 2));
```

### Other Methods

```javascript
// reverse
array.reverse();

// join - array to string
let str = array.join();

// split - string to array
let str3 = "g,t,r,e";
let arr3 = str3.split(",");

// concat
let firstArr = [1, 2, 3];
let secondArr = [4, 5, 6];
let joinedArr = firstArr.concat(secondArr);

// spread operator
let joined = [...firstArr, ...secondArr];
```

---

## 🔹 Objects  

### Creating Objects  
```javascript
let item = {
  name: 'phone',
  price: 25000,
  quantity: 1,
  categories: ['electronics', 'phones'],
  dimensions: {
    length: 7,
    breadth: 3.5,
    height: 0.5
  }
};

console.log(item);
console.log(item.categories[0]);     // 'electronics'
console.log(item.dimensions.length); // 7
````

### Another Way to Create Object

```javascript
let item2 = new Object();
item2.name = 'charger';
item2.price = 700;
item2.quantity = 1;

console.log(item2);
```

### Accessing & Modifying Properties

```javascript
// dot notation
console.log(item.price);
item.price = 26000;
console.log(item.price);

// adding new property
item.returnable = true;
console.log(item);

// square bracket notation
console.log(item['price']);
item['returnable'] = false;

// using variable as key
let key = 'price';
item[key] = 27500;

item.key = 28000; // doesn't work (creates property literally called "key")
console.log(item);
```

### Methods in Objects

```javascript
item = {
  name: "phone",
  quantity: 1,
  price: 25000,
  buy: function(){
    console.log('item added to cart');
  },
  addToList(){
    console.log('item added to list');
  }
};

item.buy();
item.addToList();
```

---

## 🔹 Loops

### For Loop

```javascript
for(let i = 1; i <= 5; i++) {
  console.log('hello');
}

// print 1 to 5
for(let i = 1; i <= 5; i++) {
  console.log(i);
}
```

### Reverse Loop

```javascript
// print 10 to 1
for(let i = 10; i >= 1; i--) {
  console.log(i);
}
```

### While Loop

```javascript
let i = 0;
console.log('while loop');

while(i >= 1){
  console.log(i);
  i--;
}
```

### Do While Loop

```javascript
i = 0;
console.log('do while loop');

do {
  console.log(i);
  i--;
} while(i >= 1);
```

### Break & Continue

```javascript
// break example
// while(true){
//   let num = Number(prompt('enter a number'));
//   if(!isNaN(num))
//     break;
// }

console.log('continue demo');

// continue example (skip multiples of 3)
for(let i = 1; i <= 10; i++){
  if(i % 3 == 0) continue;
  console.log(i);
}
```

### For…of Loop

```javascript
let arr = ['apple','orange','grapes','mango'];

// traditional loop
for(let i = 0; i < arr.length; i++) {
  console.log(arr[i].toUpperCase());
}

// for...of
for(let fruit of arr) {
  console.log(fruit);
}
```

### For…in Loop

```javascript
let item = {
  name: "phone",
  quantity: 1,
  price: 25000
};

for(let key in item){
  console.log(item[key]);
}
```

---

## 🔹 Functions  

### Function Declaration  
```javascript
function isPositive(num) { // parameter
  return num > 0;
}

console.log(isPositive(-4)); // argument
````

```javascript
function sayHello() {
  console.log('hello');
}
sayHello();
```

### Hoisting

> JavaScript hoisting refers to the process where declarations (functions, variables, or classes)
> appear to be moved to the top of their scope during execution.

```javascript
console.log(findProduct(4, 7)); // works because of hoisting

function findProduct(a, b) {
  return a * b;
}
```

### Default Parameters

```javascript
function greet(name = 'there') {
  console.log('hi', name);
}

greet('Ram');
greet();
```

### Recursion (Factorial Example)

```javascript
function factorial(n) {
  if (n == 1) return 1;
  return n * factorial(n - 1);
}
console.log(factorial(5)); // 120
```

### Function Expressions

```javascript
let isEven = function(num) {
  return num % 2 == 0;
};
console.log(isEven(5));
```

```javascript
let arr = [2, 3, 5, 6, 10];
let findSum = function(arr) {
  let sum = 0;
  for (let val of arr) {
    sum += val;
  }
  return sum;
};
console.log(findSum(arr));
```

### Arrow Functions

```javascript
let volume = (l, b, h) => l * b * h;
console.log(volume(7, 8, 9));

let sumOfArr = arr => {
  let sum = 0;
  for (let val of arr) {
    sum += val;
  }
  return sum;
};
console.log(sumOfArr(arr));

let area = r => Math.PI * r * r;
console.log(area(5));
```

### Rest Parameters & Arguments Object

```javascript
let prod = function(...args) {
  let result = 1;
  for (let val of args) result *= val;
  return result;
};

let prod2 = function() {
  let result = 1;
  for (let i = 0; i < arguments.length; i++)
    result *= arguments[i];
  return result;
};

console.log(prod(7, 6, 5, 4));   // using rest parameters
console.log(prod2(7, 6, 5, 4));  // using arguments object
```

### Generators

```javascript
function* indexGenerator() {
  let index = 1;
  while (true) {
    yield index++;
  }
}

const gen = indexGenerator();
console.log(gen.next().value); // 1
console.log(gen.next().value); // 2
console.log(gen.next().value); // 3
```

---

## 🔹 Callback Functions

```javascript
function greetConsole(name) {
  console.log('hello', name);
}

function greetHeading(name) {
  const heading = document.querySelector('h1');
  heading.innerHTML = 'hello ' + name;
}

function greet(callback) {
  callback('Ram');
}

greet(greetConsole);
// greet(greetHeading);

// using arrow function
greet(name => {
  const heading = document.querySelector('h1');
  heading.innerHTML = 'hello ' + name;
});
```

---

## 🔹 forEach

```javascript
let arr = ['deepa', 'suresh', 'ramya'];

// using callback
arr.forEach(print);

function print(val) {
  console.log(val.toUpperCase());
}

// using arrow function
arr.forEach(val => console.log(val.toUpperCase()));

// modifying array
arr.forEach((val, index, arr) => {
  arr[index] = val.toUpperCase();
});
console.log(arr);
```

### Populating Dropdown with forEach

```javascript
arr = ['ECE', 'IT', 'CSC', 'EEE'];
arr.forEach(val => {
  const opt = document.createElement('option');
  opt.textContent = val;
  opt.value = val;
  document.getElementById('branch').appendChild(opt);
});
```

---

## 🔹 Map, Filter, Reduce

### Map

```javascript
let priceUSD = [20, 35, 13];

// convert USD → INR
let priceINR = priceUSD.map(x => x * 83);
console.log(priceINR);

// using function
function convert(val) {
  return val * 83;
}
console.log(priceUSD.map(convert));
```

```javascript
// map on array of objects
const input = [
  { name: 'John', age: 15 },
  { name: 'Radha', age: 45 },
  { name: 'Kaushik', age: 12 },
  { name: 'Anu', age: 21 },
  { name: 'Divya', age: 26 }
];

const ages = input.map(x => x.age);
console.log(ages);
```

### Filter

```javascript
let cost = [35, 234, 12, 34, 54, 123];
let lessThan100 = cost.filter(x => x < 100);
console.log(lessThan100); // [35, 12, 34, 54]
```

### Reduce

```javascript
cost = [35, 234, 12, 34, 54, 123];
let cartTotal = cost.reduce((total, el) => total + el);
console.log(cartTotal); // sum of all
```

```javascript
// frequency counter
let arr2d = [
  ["a", "b", "c"],
  ["c", "d", "f"],
  ["d", "f", "g"]
];

let count = arr2d.flat().reduce((accumulator, currVal) => {
  if (accumulator[currVal])
    accumulator[currVal]++;
  else
    accumulator[currVal] = 1;
  return accumulator;
}, {});

console.log(count);
// { a: 1, b: 1, c: 2, d: 2, f: 2, g: 1 }
```

---

## 🔹 Closures  

```javascript
let a = 100;
function func1() {
  let b, c;
  console.log('a is', a);
}
func1();

a = 200;
func1();
````

### Higher Order Functions & Lexical Scoping

A **closure** is a function bundled together with references to its surrounding state (lexical environment).
It gives access to an **outer function’s scope** from an **inner function**.

```javascript
function outer(name) {
  let outerVariable = 'Bread';
  function inner() {
    let innerVariable = 'Butter';
    console.log('inner variable', innerVariable);
    console.log('outer variable', outerVariable);
    console.log('a is', a);
    console.log('hello', name);
  }
  return inner;
}

let call1 = outer('Vidya');
call1();

let call2 = outer('John');
call2();
call1();
```

### Function Returning Function

```javascript
function makeAdder(x) {
  return function(y) {
    return x + y;
  }
}

let add5 = makeAdder(5);
console.log(add5(10));   // 15

let add100 = makeAdder(100);
console.log(add100(20)); // 120
console.log(add100(45)); // 145
console.log(add5(22));   // 27
```

---

## 🔹 Memory Management

### Primitive Types (Copied by Value)

```javascript
let a = 100;
a = 200;
let b = a;
b = 300;

console.log('a is', a); // 200
console.log('b is', b); // 300
```

### Reference Types (Objects & Arrays share references)

```javascript
let obj1 = { name: 'Danya', age: 24 };
let obj2 = obj1;

obj1.age = 25;
obj2.name = 'Ramya';

console.log('obj1', obj1); // {name:'Ramya', age:25}
console.log('obj2', obj2); // {name:'Ramya', age:25}
```

```javascript
let arr1 = [2, 3, 4];
let arr2 = arr1;

arr2[0] = 10;

console.log(arr1, arr2); // both modified
```

### BigInt

```javascript
let bigNum = 9007199254740991n;
const bigNum2 = BigInt(9007199254740991);
```

---

## 🔹 Set

A **Set** is a collection of **unique values**.

```javascript
let arr = [1, 1, 2, 3, 4, 5, 5, 5, 10, 8];
let mySet1 = new Set(arr);
console.log(mySet1); // {1,2,3,4,5,10,8}

let mySet2 = new Set();
mySet2.add(4);
mySet2.add(5);
mySet2.add('pqr');
mySet2.add({ a: 1, b: 2 });
mySet2.add(4); // ignored since duplicate
console.log(mySet2);
```

```javascript
let obj = { a: 1, b: 2 };
mySet2.add(obj);
console.log(mySet2);

console.log(mySet2.size);    // size of set
console.log(mySet2.has(6));  // false
console.log(mySet2.delete(4)); // removes 4

let arr2 = Array.from(mySet2); // convert to array
console.log(arr2);
```

---

## 🔹 Map

A **Map** stores **key-value pairs**.

* Keys are unique
* Keys can be objects

```javascript
let map1 = new Map();
map1.set('a', 1);
map1.set('b', 2);
map1.set('a', 3); // overwrites key 'a'

console.log(map1);
console.log(map1.size);     // 2
console.log(map1.has('c')); // false

map1.delete('a');
map1.set('d', 2);
map1.set('e', 3);
```

### Iterating Over Maps

```javascript
for (let i of map1) {
  console.log(i);
}

for (let [k, v] of map1) {
  console.log(k, v);
}

for (let k of map1.keys()) {
  console.log(k);
}

map1.forEach((v, k) => {
  console.log('key', k, 'value', v);
});
```

### Converting Between Map & Array

```javascript
// 2D array → Map
let kvArray = [['a', 1], ['b', 1]];
let map2 = new Map(kvArray);
console.log(map2);

// Map → Array
console.log(...map2);
```
---

## 🔹 Object-Oriented Programming (OOP)  

### Object Literals  
```javascript
let user1 = {
  name: 'Ramya',
  age: 22,
  login() {
    console.log('You are logged in');
  },
  logout() {
    console.log('You are logged out');
  }
};

let user2 = {
  name: 'Vasanth',
  age: 24,
  login() {
    console.log('Hi', this.name);
    console.log('You are logged in');
  },
  logout() {
    console.log('You are logged out');
  }
};

let user3 = {
  name: 'John',
  age: 21,
  login() {
    console.log('Hi', this.name);
    console.log('You are logged in');
  },
  logout() {
    console.log('You are logged out');
  }
};

user2.login();
user3.login();
````

---

### Classes in ES6

```javascript
class User { // base/parent class
  static numberOfUsers = 0;

  constructor(name, age) {
    this.name = name;
    this.age = age;
    User.numberOfUsers++;
  }

  login() {
    console.log('Hi', this.name);
    console.log('You are logged in');
  }

  logout() {
    console.log('You are logged out');
  }

  static displayTotalUsers() {
    console.log('Total number of Users is ' + User.numberOfUsers++);
  }
}

let userOne = new User('Vidya', 21);
let userTwo = new User('Ramesh', 33);
let userThree = new User('Mano', 32);

userOne.login();
userTwo.logout();

User.displayTotalUsers();
```

---

### Inheritance

```javascript
class Paiduser extends User {
  constructor(name, age) {
    super(name, age);
    this.storage = 100;
  }

  message() {
    console.log('You have 100GB free storage');
  }

  // overriding
  login() {
    console.log('Thank you for your support');
    return this; // for method chaining
  }
}

let paidUser1 = new Paiduser('Dhana', 22);
paidUser1.login();
paidUser1.message();

// method chaining
paidUser1.login().message();
```

---

### Prototypes

```javascript
function User(name, age) {
  this.name = name;
  this.age = age;
}

User.prototype.login = function() {
  console.log('hi', this.name);
  console.log('You are logged in');
};

let user1 = new User('Abdul', 34);
user1.login();
```

---

### Getters & Setters

```javascript
class Temperature {
  constructor(temp) {
    this._temp = temp;
  }

  get temp() {
    return `${this._temp} deg celcius`;
  }

  set temp(temp) {
    if (temp > 100) temp = 100;
    this._temp = temp;
  }
}

let temp1 = new Temperature(25);
temp1.temp = 150;
console.log(temp1.temp); // 100 deg celcius
```

---

## 🔹 Modules (ES6)

**script.js**

```javascript
import C, { fillGas as fill, repair } from './car.js';

let car1 = new C();
car1.drive();
fill();
```

**car.js**

```javascript
export default class Car {
  drive() {
    console.log("Driving");
  }
}

export function fillGas() {
  console.log('Filling Gas');
}

export function repair() {
  console.log('Repairing');
}
```

---

## 🔹 Asynchronous JavaScript & Event Loop

```javascript
console.log('Hello..'); // f1

function sync() {
  console.log('step 1'); // f3
  console.log('step 2'); // f4
  console.log('step 3'); // f5
}
sync(); // f2

let a = 100;
let b = 20;
let c = a + b;

setTimeout(() => console.log('step1'), 0);     // f6
setTimeout(() => console.log('step2'), 2000);  // f7
setTimeout(() => console.log('step3'), 1000);  // f8

console.log('bye'); // f9

// setInterval(() => console.log("Hi.."), 2000);
```
---

## 🔹 Promises  

```javascript
// The Promise object represents the eventual completion (or failure) of an async operation
function tatkalBook() {
  return new Promise((resolve, reject) => {
    let bookingSuccess = false;
    if (bookingSuccess) resolve(850);
    else reject();
  });
}

// tatkalBook()
//   .then((amt) => console.log(`Thanks buddy! Rs.${amt} transferred`))
//   .catch(() => console.log("Thanks for trying! I will book a bus"));

function tossCoin() {
  return new Promise((resolve, reject) => {
    // 0 - head(success), 1 - tail(failure)
    const rand = Math.floor(Math.random() * 2);
    if (rand == 0) resolve();
    else reject();
  });
}

// tossCoin()
//   .then(() => console.log("Congrats! It's head! You won"))
//   .catch(() => console.log("Sorry! You lost! It's tail"));
````

### Multiple Promises

```javascript
let reachA = new Promise((resolve, reject) => {
  const reached = true;
  if (reached) setTimeout(resolve, 3000, "Vidya reached");
  else reject("Vidya not reached");
});

let reachB = new Promise((resolve, reject) => {
  const reached = true;
  if (reached) setTimeout(resolve, 1000, "Ramya reached");
  else reject("Ramya not reached");
});

let reachC = new Promise((resolve, reject) => {
  const reached = true;
  if (reached) setTimeout(resolve, 2000, "Latha reached");
  else reject("Latha not reached");
});

// Run promises together
Promise.all([reachA, reachB, reachC])
  .then((message) => console.log(message))
  .catch((message) => console.log(message));

// All settled (resolved or rejected)
Promise.allSettled([reachA, reachB, reachC])
  .then((message) => console.log(message));

// First successful one
Promise.any([reachA, reachB, reachC])
  .then((message) => console.log(message));

// First settled (whichever resolves/rejects first)
Promise.race([reachA, reachB, reachC])
  .then((message) => console.log(message));
```

---

## 🔹 Error Handling

```javascript
try {
  num = prompt("Enter a number");
  if (num === '') throw 'Cannot be empty';
  if (isNaN(num)) throw "Enter a valid Number";
  console.log(num ** 2);
} catch (error) {
  console.log(error);
} finally {
  console.log('bye');
}
```

---

## 🔹 Async / Await

```javascript
// async function always returns a promise
async function fn1() {
  return 'hello';
}

console.log(fn1());
fn1().then((msg) => console.log('success ' + msg));

let reachA = new Promise((resolve, reject) => {
  const reached = true;
  if (reached) setTimeout(resolve, 3000, "Vidya reached");
  else reject("Vidya not reached");
});

async function asyncstatus() {
  try {
    console.log('hi..');
    let res = await reachA;
    console.log(res);
    console.log('bye');
  } catch (err) {
    console.log(err);
  }
}
asyncstatus();
```

---

## 🔹 JSON

```javascript
let json1 = "Hello";
let json2 = 3;
let json3 = true;
let json4 = [4, 5, 6, 7];

let json5 = `{
  "Stock": "TCS",
  "Price": 3500
}`;

let json6 = `[
  { "Stock": "TCS", "Price": 3500 },
  { "Stock": "HUL", "Price": 2500 },
  { "Stock": "SBI", "Price": 550 }
]`;

let parsed = JSON.parse(json6);
console.log(parsed[1].Price); // 2500

console.log(JSON.stringify(parsed));
```

---

## 🔹 Fetch API

```javascript
// Fetching data from API
fetch('https://official-joke-api.appspot.com/jokes/programming/random')
  .then((res) => res.json())
  .then((msg) => console.log(msg[0].setup, msg[0].punchline))
  .catch((err) => console.log(err));

// Fetching Thirukkural API
fetch('https://api-thirukkural.vercel.app/api?num=25')
  .then(res => {
    if (res.ok) console.log('success');
    else console.log('Failed');
    return res.json();
  })
  .then(msg => console.log(msg.line1, msg.line2, msg.tam_exp))
  .catch(err => console.log(err));
```

### CRUD with Fetch

```javascript
// GET
fetch('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => response.json())
  .then(json => console.log(json));

// POST
fetch('https://jsonplaceholder.typicode.com/todos', {
  method: 'POST',
  headers: { 'content-type': 'application/json' },
  body: JSON.stringify({
    userId: 22,
    id: 456,
    title: 'test',
    completed: false
  })
})
  .then(response => response.json())
  .then(json => console.log(json));
```

# 📊 Mini JavaScript Projects  

This repository contains simple JavaScript projects built as part of learning exercises.  

---

## 🏦 FD Rate Calculator  

### 📌 Overview  
A simple **Fixed Deposit Rate Calculator** that determines the interest rate based on tenure in months.  

### ⚙️ Features  
- Takes **tenure in months** as input.  
- Calculates **FD interest rate** based on conditions.  
- Displays result dynamically.  

### 🖥️ Demo Code  

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <title>FD Rate Calculator</title>
</head>
<body>
  <div id="wrapper">
    <h2>FD Rate Calculator</h2>
    <div class="inputdiv">
      <input type="text" id="input" placeholder="tenure months">
    </div>
    <div>
      <button type="submit" onclick="fdRate()">Calculate</button>
    </div>
    <div id="result"></div>
  </div>

  <script>
    function fdRate(){
      const months = Number(document.getElementById("input").value)
      let rate = 0
      
      if(months < 3)
        rate = 5.8
      else if(months >= 3 && months <= 6)
        rate = 6.5
      else if(months >= 7 && months <= 9)
        rate = 6.8
      else
        rate = 7

      let result = document.querySelector('#result')
      result.innerHTML = "Your interest rate is " + rate + "%"
    }
  </script>
</body>
</html>
````

---

## 🏙️ City Stats Tool

### 📌 Overview

A **City Statistics Tool** that shows details like **population, literacy rate, and language** of selected Indian cities.

### ⚙️ Features

* Select city from a dropdown.
* Uses **switch case** for stats.
* Displays city data dynamically.

#### HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <title>City Stats</title>
</head>
<body>
  <div id="wrapper">
    <h2>Select a City</h2>
    <div class="inputdiv">
      <select id="input">
        <option value="Bengaluru">Bengaluru</option>
        <option value="Chennai">Chennai</option>
        <option value="Delhi">Delhi</option>
        <option value="Mumbai">Mumbai</option>
      </select>
    </div>
    <div>
      <button type="submit">Show Stats</button>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>
```

#### CSS

```css
html, body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
  background-color: #f5e8ba;
}

#wrapper div, #wrapper h2 {
  display:flex;
  justify-content: center;
}

h2 {
  color: #ffeba7;
  letter-spacing: 1px;
}

select {
  border-radius: 5px;
  border: 2px solid black;
  margin-top: 30px;
  height: 2.5em;
  width: 250px;
  padding-left: 10px;
}

#wrapper {
  height: 500px;
  width: 400px;
  margin: 200px auto;
  background-color: #1f2029;
  border-radius: 10px;
  padding: 30px;
}

button {
  margin-top: 20px;
  background-color: #ffeba7;
  border-radius: 4px;
  height: 44px;
  font-weight: 600;
  padding: 0 30px;
  letter-spacing: 1px;
  border: none;
  color: #102770;
}

button:hover {
  cursor: pointer;
}

#result {
  color: white;
  margin-top: 20px;
  font-size: 32px;
}
```

#### JavaScript

```js
const button = document.querySelector('button')
let resultdiv = document.createElement('div')
resultdiv.id = 'result'
document.getElementById('wrapper').appendChild(resultdiv)

button.addEventListener('click', displayStats)

function displayStats(){
  const input = document.getElementById("input")
  const city = input.options[input.selectedIndex].value
  let population = 0, literacyRate = 0, language = ''

  switch(city){
    case 'Bengaluru':
      population = 8443675
      literacyRate = 88.71
      language = 'Kannada'
      break
    case 'Chennai':
      population = 4646732
      literacyRate = 90.20
      language = 'Tamil'
      break
    case 'Mumbai':
      population = 12442373
      literacyRate = 89.73
      language = 'Marathi'
      break
    case 'Delhi':
      population = 16787941
      literacyRate = 86.20
      language = 'Hindi'
      break
  }

  let text = `The Indian city of ${city} has a population of ${population}. Language spoken is ${language} with a literacy rate of ${literacyRate}%.`
  document.getElementById('result').innerHTML = text
}
```

---

# 🎨 Color Flipper  

A fun JavaScript project that generates random **hex colors** and changes the background dynamically when you click the button.  

---

## 📌 Features  
- Displays **random hex color codes**.  
- Updates **background color** dynamically.  
- Shows current **color code** on the screen.  

---

### HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <title>Color Flipper</title>
</head>
<body>
  <div id="heading">Color Flipper
    <span id="color">#FFFFFF</span>
  </div>
  <div id="wrap">
    <div id="container">
      <button id="btn">click me</button>
    </div>
  </div>
  <script src="app.js"></script>
</body>
</html>
````

### CSS

```css
html, body {
  margin: 0;
  font-family: 'Apple Chancery', cursive;
}

#heading {
  text-align: left;
  font-size: 2em;
  margin: 5px 15px;
  color: crimson;
}

#color {
  float: right;
  margin-right: 15px;
}

#wrap {
  height: 90vh;
  width: 100vw;
  border-top: 3px solid #323232;
  display: flex;
  align-items: center;
  justify-content: center;
}

button {
  border: 1px solid black;
  background-color: rgb(219, 54, 54);
  color: white;
  border-radius: 15px;
  padding: 20px 80px;
  font-size: 28px;
  letter-spacing: 5px;
  cursor: pointer;
}
```

### JavaScript

```js
const btn = document.getElementById("btn");
const colortext = document.getElementById("color");
const wrap = document.getElementById("wrap");

const hex = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 'A', 'B', 'C', 'D', 'E', 'F'];

btn.addEventListener('click', function() {
  let hexColor = '#';
  for (let i = 1; i <= 6; i++) {
    hexColor += randHexValue();
  }
  wrap.style.backgroundColor = hexColor;
  colortext.innerHTML = hexColor;
});

function randHexValue() {
  let randomIndex = Math.floor(Math.random() * 16);
  return hex[randomIndex];
}
```

---

# ⏰ Digital Clock  

A simple **Digital Clock** built using **HTML, CSS, and JavaScript**. It displays the current time with **hours, minutes, seconds, and AM/PM indicator**, updating in real-time.  

---

## 📌 Features  
- Real-time digital clock display.  
- Automatic **AM/PM** format handling.  
- Styled with gradient background and large fonts.  
- Fully responsive and minimal design.  

---


### HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <title>Digital Clock</title>
</head>
<body>
  <div class="container">
    <div id="wrapper">
      <span id="hours">00</span>
      <span>:</span>
      <span id="mins">00</span>
      <span>:</span>
      <span id="seconds">00</span>
      <span id="ampm">AM</span>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>
````

### CSS

```css
body {
  margin: 0;
  padding: 0;
  background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(9,98,121,1) 35%, rgba(0,212,255,1) 100%);
}

.container {
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  color: white;
  display: flex;
  width: 100vw;
  height: 100vh;
  align-items: center;
  justify-content: center;
  font-size: 5rem;
}

#wrapper {
  border: 3px solid white;
  padding: 1rem;
}

.container span {
  margin-left: 10px;
}

#ampm {
  font-size: 3rem;
  align-items: end;
}
```

### JavaScript

```js
const ampm = document.getElementById('ampm');

function displayTime() {
  let dateTime = new Date();
  let hr = dateTime.getHours();
  let min = padZero(dateTime.getMinutes());
  let sec = padZero(dateTime.getSeconds());

  if (hr > 12) {
    ampm.innerHTML = 'PM';
    hr = hr - 12;
  } else {
    ampm.innerHTML = 'AM';
  }

  hr = padZero(hr);
  document.getElementById('hours').innerHTML = hr;
  document.getElementById('mins').innerHTML = min;
  document.getElementById('seconds').innerHTML = sec;
}

function padZero(num) {
  return num < 10 ? "0" + num : num;
}

setInterval(displayTime, 100);
```

---

# 💱 Currency Converter  

A simple **Currency Converter** app built using **HTML, CSS, and JavaScript**, which uses the **Frankfurter API** to fetch real-time exchange rates.  

---

## 📌 Features  
- Convert between any two currencies.  
- Real-time exchange rates using [Frankfurter API](https://www.frankfurter.app/).  
- Validations (prevents selecting the same currency).  
- Simple and responsive UI.  

---


### HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <title>Currency Convertor</title>
</head>
<body>
  <div class="container">
    <h1>Currency Convertor</h1>
    <div class="box">
      <div class="left-box">
        <select name="currency" class="currency"></select>
        <input type="number" id="input">
      </div>
      <div class="right-box">
        <select name="currency" class="currency"></select>
        <input type="number" id="result">
      </div>
    </div>
    <div class="btn">
      <button id="btn">Convert</button>
    </div>
  </div>
  <script src="app.js"></script>
</body>
</html>
````

### CSS

```css
html, body {
  font-family: 'Poppins', sans-serif;
  background-color: #f5e8ba;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.container {
  background-color: #1f2029;
  padding: 10px 24px;
  border-radius: 20px;
  width: 490px;
}

h1 {
  color: #ffeba7;
  text-align: center;
  margin-bottom: 0.5em;
}

.container .box {
  width: 100%;
  display: flex;
}

select, input {
  width: 95%;
  height: 40px;
  font-size: 1.2em;
  border-radius: 10px;
  border: none;
  margin: 0.2em 0;
  padding: 0 1em;
}

select {
  background-color: coral;
  cursor: pointer;
}

input {
  background: #cccccc;
  outline: none;
}

button {
  width: 50%;
  height: 40px;
  background-color: #ffeba7;
  color: #102770;
  border-radius: 10px;
  border: none;
  cursor: pointer;
  font-size: 1em;
}
```

### JavaScript

```js
let select = document.querySelectorAll('.currency');
let btn = document.getElementById('btn');
let input = document.getElementById('input');

fetch('https://api.frankfurter.app/currencies')
  .then(res => res.json())
  .then(res => displayDropDown(res));

function displayDropDown(res) {
  let curr = Object.entries(res);
  for (let i = 0; i < curr.length; i++) {
    let opt = `<option value="${curr[i][0]}">${curr[i][0]}</option>`;
    select[0].innerHTML += opt;
    select[1].innerHTML += opt;
  }
}

btn.addEventListener('click', () => {
  let curr1 = select[0].value;
  let curr2 = select[1].value;
  let inputVal = input.value;
  if (curr1 === curr2) {
    alert("Choose different currencies");
  } else {
    convert(curr1, curr2, inputVal);
  }
});

function convert(curr1, curr2, inputVal) {
  const host = 'api.frankfurter.app';
  fetch(`https://${host}/latest?amount=${inputVal}&from=${curr1}&to=${curr2}`)
    .then(resp => resp.json())
    .then(data => {
      document.getElementById('result').value = Object.values(data.rates)[0];
    });
}
```

---

# 📝 ToDo List

A **ToDo List app** built using **HTML, CSS, and JavaScript** with **Local Storage** support.

---

## 📌 Features

* Add new tasks.
* Strike-through tasks when clicked.
* Double-click to delete tasks.
* Stores tasks in **Local Storage** so they persist after page reload.

---

### HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <title>ToDo List</title>
</head>
<body>
  <div id="wrapper">
    <h2>Todo List</h2>
    <input type="text" id="input">
    <button id="add">Add</button>
    <div id="todoList"></div>
  </div>
  <script src="app.js"></script>
</body>
</html>
```

### CSS

```css
html, body {
  margin: 0;
  font-family: 'Poppins', sans-serif;
  background-color: #f5e8ba;
}

#wrapper {
  height: 500px;
  width: 400px;
  margin: 200px auto;
  background-color: #1f2029;
  border-radius: 10px;
  padding: 30px;
}

h2 {
  color: #ffeba7;
  text-align: center;
}

input {
  border-radius: 5px;
  border: 2px solid black;
  margin-top: 30px;
  height: 2.5em;
  width: 250px;
  padding-left: 10px;
}

button {
  margin-top: 20px;
  background-color: #ffeba7;
  border-radius: 4px;
  height: 44px;
  font-weight: 600;
  padding: 0 30px;
  border: none;
  color: #102770;
  cursor: pointer;
}

#todoList {
  color: white;
  font-size: 28px;
  margin-top: 10px;
}

#todoList p {
  margin: 10px 0;
  cursor: pointer;
}
```

### JavaScript

```js
let button = document.getElementById('add');
let todoList = document.getElementById('todoList');
let input = document.getElementById('input');
let todos = [];

window.onload = () => {
  todos = JSON.parse(localStorage.getItem('todos')) || [];
  todos.forEach(todo => addtodo(todo));
};

button.addEventListener('click', () => {
  todos.push(input.value);
  localStorage.setItem('todos', JSON.stringify(todos));
  addtodo(input.value);
  input.value = '';
});

function addtodo(todo) {
  let para = document.createElement('p');
  para.innerText = todo;
  todoList.appendChild(para);

  para.addEventListener('click', () => {
    para.style.textDecoration = 'line-through';
    remove(todo);
  });

  para.addEventListener('dblclick', () => {
    todoList.removeChild(para);
    remove(todo);
  });
}

function remove(todo) {
  let index = todos.indexOf(todo);
  if (index > -1) {
    todos.splice(index, 1);
  }
  localStorage.setItem('todos', JSON.stringify(todos));
}
```

---

# ✅ Form Validation  

A **Form Validation project** using **HTML, CSS, and JavaScript**.  
This app validates **username, email, password, and confirm password** fields with real-time error messages.  

---

## 📌 Features  
- Username, email, password, and confirm password validation.  
- Email format validation using **Regex**.  
- Password must be at least **8 characters**.  
- Error/success indicators with colored borders.  

---


### HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <link rel="stylesheet" href="style.css">
  <script src="app.js" defer></script>
  <title>Register</title>
</head>
<body>
  <div class="container">
    <form id="form">
      <h1>Register</h1>
      <div class="input-group">
        <label for="username">Username</label>
        <input type="text" id="username">
        <div class="error"></div>
      </div>
      <div class="input-group">
        <label for="email">Email</label>
        <input type="text" id="email">
        <div class="error"></div>
      </div>
      <div class="input-group">
        <label for="password">Password</label>
        <input type="password" id="password">
        <div class="error"></div>
      </div>
      <div class="input-group">
        <label for="cpassword">Confirm Password</label>
        <input type="password" id="cpassword">
        <div class="error"></div>
      </div>
      <button type="submit">Register</button>
    </form>
  </div>
</body>
</html>
````

### CSS

```css
body {
  background: linear-gradient(0deg, rgba(34,193,195,1) 0%, rgba(121,32,153,1) 100%);
  background-attachment: fixed;
  margin: 0;
  font-family: 'Poppins', sans-serif;
}

#form {
  width: 400px;
  margin: 20vh auto;
  background-color: whitesmoke;
  border-radius: 5px;
  padding: 30px;
}

h1 {
  text-align: center;
  color: #792099;
}

.input-group {
  display: flex;
  flex-direction: column;
  margin-bottom: 15px;
}

.input-group input {
  border-radius: 5px;
  font-size: 20px;
  margin-top: 5px;
  padding: 10px;
  border: 1px solid rgb(34,193,195);
}

.input-group .error {
  color: rgb(242, 18, 18);
  font-size: 16px;
}

.input-group.success input {
  border-color: #0cc477;
}

.input-group.error input {
  border-color: rgb(206, 67, 67);
}
```

### JavaScript

```js
const form = document.querySelector('#form');
const username = document.querySelector('#username');
const email = document.querySelector('#email');
const password = document.querySelector('#password');
const cpassword = document.querySelector('#cpassword');

form.addEventListener('submit',(e)=>{
  if(!validateInputs()){
    e.preventDefault();
  }
});

function validateInputs(){
  const usernameVal = username.value.trim();
  const emailVal = email.value.trim();
  const passwordVal = password.value.trim();
  const cpasswordVal = cpassword.value.trim();
  let success = true;

  if(usernameVal === ''){
    success=false;
    setError(username,'Username is required');
  } else setSuccess(username);

  if(emailVal === ''){
    success=false;
    setError(email,'Email is required');
  } else if(!validateEmail(emailVal)){
    success=false;
    setError(email,'Please enter a valid email');
  } else setSuccess(email);

  if(passwordVal === ''){
    success=false;
    setError(password,'Password is required');
  } else if(passwordVal.length < 8){
    success=false;
    setError(password,'Password must be atleast 8 characters');
  } else setSuccess(password);

  if(cpasswordVal === ''){
    success=false;
    setError(cpassword,'Confirm password is required');
  } else if(cpasswordVal !== passwordVal){
    success=false;
    setError(cpassword,'Passwords do not match');
  } else setSuccess(cpassword);

  return success;
}

function setError(element, message){
  const inputGroup = element.parentElement;
  const errorElement = inputGroup.querySelector('.error');
  errorElement.innerText = message;
  inputGroup.classList.add('error');
  inputGroup.classList.remove('success');
}

function setSuccess(element){
  const inputGroup = element.parentElement;
  const errorElement = inputGroup.querySelector('.error');
  errorElement.innerText = '';
  inputGroup.classList.add('success');
  inputGroup.classList.remove('error');
}

const validateEmail = (email) => {
  return String(email).toLowerCase().match(
    /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
  );
};
```
---
# 📌 Navbar Project  

A **responsive navigation bar** built using **HTML, CSS, and JavaScript**.  
It includes a **hamburger menu** for smaller screens and adapts seamlessly to mobile devices.  

---

## ✨ Features  
- Responsive navigation bar.  
- Hamburger menu toggle on small screens.  
- Hover effect on links.  
- Mobile-first design using **media queries**.  

---
### HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <title>NavBar Demo</title>
</head>
<body>
  <nav>
    <div class="logo">
      <a href="#">Matrix</a>
    </div>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">Services</a></li>
      <li><a href="#">About</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
    <div class="menu">
      <div class="menu-line"></div>
      <div class="menu-line"></div>
      <div class="menu-line"></div>
    </div>
  </nav>
</body>
<script>
  const menu = document.querySelector('.menu');
  const menuList = document.querySelector('nav ul');
  menu.addEventListener('click',()=>{
    menuList.classList.toggle('showmenu');
  });
</script>
</html>
````

### CSS

```css
body {
  margin: 0;
  padding: 0;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  background-image: url('bg.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  height: 100vh;
}

nav {
  background-color: darksalmon;
  font-size: 28px;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-around;
  color: darkslateblue;
}

nav li {
  display: inline-block;
  margin: 0 8px;
}

nav a {
  text-decoration: none;
}

.logo {
  font-size: 36px;
  font-weight: bolder;
}

nav a:hover {
  color: whitesmoke;
}

.menu-line {
  height: 3px;
  width: 20px;
  background-color: darkslateblue;
  margin-bottom: 3px;
}

.menu {
  cursor: pointer;
  display: none;
}

/* Mobile Responsive */
@media all and (max-width:640px) {
  nav {
    flex-direction: column;
  }
  nav li {
    display: block;
    padding: 10px 0;
  }
  ul {
    text-align: center;
    padding: 0;
    display: none;
  }
  .logo {
    align-self: flex-start;
    margin: 10px 0px 0px 30px;
  }
  .menu {
    display: block;
    position: absolute;
    right: 20px;
    top: 25px;
  }
  .showmenu {
    display: block;
  }
}
```

---
# 📸 Image Slider  

A simple and elegant **Image Slider** built using **HTML, CSS, and JavaScript**.  
The slider allows users to navigate images using **left and right buttons**.  

---

## ✨ Features  
- Image slider with smooth transitions.  
- Left and right navigation buttons.  
- Responsive design.  
- Easy to customize by adding more images.  

---


### HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
  <script src="app.js" defer></script>
  <title>Image Slider</title>
</head>
<body>
  <div class="container">
    <a class="btn btn-left"><i class="fa-solid fa-caret-left"></i></a>
    <a class="btn btn-right"><i class="fa-solid fa-caret-right"></i></a>
  </div>
</body>
</html>
````

### CSS

```css
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: salmon;
}

.container {
  min-height: 80vh;
  width: 60%;
  border: 8px solid rgb(129, 187, 174);
  margin: 4rem auto;
  border-radius: 5px;
  box-shadow: 10px 10px 35px rgba(0,0,0,0.6);
  position: relative;
  background: url("Imgs/1.jpg") center/cover fixed no-repeat;
  transition: background 1s ease-in-out;
}

.btn-left {
  position: absolute;
  top: 50%;
  left: -2%;
  background-color: white;
  padding: .4em .6em;
  border-radius: 2em;
  transform: translateY(calc(-50%));
  cursor: pointer;
}

.btn-right {
  position: absolute;
  top: 50%;
  right: -2%;
  background-color: white;
  padding: .4em .6em;
  border-radius: 2em;
  transform: translateY(calc(-50%));
  cursor: pointer;
}
```

### JavaScript

```javascript
const container = document.querySelector('.container');
const btns = document.querySelectorAll('.btn');
const imgList = ["1","2","3","4"];
let index = 0;

btns.forEach((button) => {
  button.addEventListener('click', () => {
    if (button.classList.contains('btn-left')) {
      index--;
      if (index < 0) {
        index = imgList.length - 1;
      }
    } else {
      index++;
      if (index === imgList.length) {
        index = 0;
      }
    }
    container.style.background = `url("Imgs/${imgList[index]}.jpg") center/cover fixed no-repeat`;
  });
});
```

---


# 🃏 Memory Game  

A fun **Memory Matching Game** built using **HTML, CSS, and JavaScript**.  
Flip two cards at a time and try to match all pairs.  

---

## ✨ Features  
- Shuffle cards at the start of each game.  
- Flip cards to reveal icons (FontAwesome).  
- Matches stay revealed, mismatches flip back.  
- Winning screen when all pairs are matched.  

---

### HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
  <link rel="stylesheet" href="style.css">
  <script src="mem.js" defer></script>
  <title>Memory Game</title>
</head>
<body>
  <h3>Memory Game</h3>
  <div id="gameBoard" class="game"></div>
</body>
</html>
````

### CSS

```css
body {
  margin: 0;
  padding: 0;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  background-color: #f5e8ba;
}

h3 {
  font-size: 2rem;
  text-align: center;
  color: crimson;
}

.game {
  display: grid;
  margin: 40px auto;
  grid-template-columns: repeat(4, 120px);
  grid-row-gap: 2em;
  align-items: center;
  justify-content: center;
}

#gameBoard div {
  height: 150px;
  width: 80px;
  border: 2px solid rgb(151, 151, 202);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2em;
  color: brown;
  background-color: #e5e5f7;
}

.cardback {
  background-color: #e5e5f7;
  opacity: 0.8;
  background-image: linear-gradient(135deg, #444cf7 25%, transparent 25%);
  background-size: 10px 10px;
  background-repeat: repeat;
}

#gameBoard div:hover {
  cursor: pointer;
}

.won {
  font-size: 3em;
  display: flex;
  justify-content: center;
  height: 500px;
  align-items: center;
  color: blue;
  width: 500px;
  margin: 0px auto;
}
```

### JavaScript

```javascript
const cardsArray = [
  { name: 'dog', icon: '<i class="fa-solid fa-dog"></i>' },
  { name: 'hippo', icon: '<i class="fa-solid fa-hippo"></i>' },
  { name: 'fish', icon: '<i class="fa-solid fa-fish"></i>' },
  { name: 'cat', icon: '<i class="fa-solid fa-cat"></i>' },
  { name: 'spider', icon: '<i class="fa-solid fa-spider"></i>' },
  { name: 'frog', icon: '<i class="fa-solid fa-frog"></i>' },
  { name: 'dog', icon: '<i class="fa-solid fa-dog"></i>' },
  { name: 'hippo', icon: '<i class="fa-solid fa-hippo"></i>' },
  { name: 'fish', icon: '<i class="fa-solid fa-fish"></i>' },
  { name: 'cat', icon: '<i class="fa-solid fa-cat"></i>' },
  { name: 'spider', icon: '<i class="fa-solid fa-spider"></i>' },
  { name: 'frog', icon: '<i class="fa-solid fa-frog"></i>' }
];

let flippedCards = [];
let matchedPairs = 0;

shuffleCards();
const gameBoard = document.getElementById('gameBoard');
displayCards();

function shuffleCards() {
  for (let i = cardsArray.length - 1; i >= 0; i--) {
    const randIndex = Math.floor(Math.random() * (i + 1));
    [cardsArray[i], cardsArray[randIndex]] = [cardsArray[randIndex], cardsArray[i]];
  }
}

function displayCards() {
  cardsArray.forEach((curr, index) => {
    const card = document.createElement('div');
    card.setAttribute('id', index);
    card.classList.add('cardback', 'active');
    gameBoard.append(card);
    card.addEventListener('click', flipCard);
  });
}

function flipCard() {
  if (flippedCards.length < 2 && this.classList.contains('active')) {
    let cardId = this.getAttribute('id');
    flippedCards.push(this);
    this.classList.remove('cardback');
    this.innerHTML = cardsArray[cardId].icon;
    if (flippedCards.length === 2) {
      setTimeout(checkMatch, 1000);
    }
  }
}

function checkMatch() {
  const card1Id = flippedCards[0].getAttribute('id');
  const card2Id = flippedCards[1].getAttribute('id');

  if (cardsArray[card1Id].name === cardsArray[card2Id].name) {
    flippedCards.forEach(card => {
      card.style.border = 'none';
      card.style.backgroundColor = '#f5e8ba';
      card.innerHTML = '';
      card.classList.remove('active');
    });
    matchedPairs++;
    checkGameOver();
  } else {
    flippedCards.forEach(card => {
      card.innerHTML = '';
      card.classList.add('cardback');
    });
  }
  flippedCards = [];
}

function checkGameOver() {
  if (matchedPairs === cardsArray.length / 2) {
    while (gameBoard.firstChild) {
      gameBoard.removeChild(gameBoard.firstChild);
    }
    gameBoard.innerHTML = 'You Won 🎉';
    gameBoard.classList.remove('game');
    gameBoard.classList.add('won');
  }
}
```

# 🐍 Snake Game  

A classic **Snake Game** built with **HTML, CSS, and JavaScript**.  
Control the snake, eat food to grow, and avoid hitting walls or yourself.  

---

## ✨ Features  
- Snake moves across the board and grows when eating food.  
- Real-time score updates.  
- Game Over detection when hitting walls or self.  
- Pause/Resume using **Spacebar**.  
- Smooth gameplay using `canvas`.  

---

### HTML
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <script src="app.js" defer></script>
  <title>Snake Game</title>
</head>
<body>
  <h2>Snake Game</h2>
  <div id="msg">Press space to pause or continue</div>
  <div id="container">
    <canvas id="gameBoard" width="500" height="500"></canvas>
    <div id="score">Score: <span id="scoreVal">0</span></div>
  </div>
</body>
</html>
````

### CSS

```css
* {
  margin: 0;
  padding: 0;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  background-color: #f5e8ba;
  text-align: center;
}

h2 {
  color: darkgreen;
}

#msg {
  margin-bottom: 1em;
}

#gameBoard {
  border: 3px solid;
}

#score {
  margin-top: 1em;
  font-size: 2em;
}
```

### JavaScript

```javascript
const gameBoard = document.getElementById('gameBoard');
const context = gameBoard.getContext('2d');
const scoreText = document.getElementById('scoreVal');
const WIDTH = gameBoard.width;
const HEIGHT = gameBoard.height;
const UNIT = 25;

let foodX, foodY;
let xVel = 25;
let yVel = 0;
let score = 0;
let active = true;
let started = false;
let paused = false;

let snake = [
  { x: UNIT * 3, y: 0 },
  { x: UNIT * 2, y: 0 },
  { x: UNIT, y: 0 },
  { x: 0, y: 0 }
];

window.addEventListener('keydown', keyPress);
startGame();

function startGame() {
  context.fillStyle = '#212121';
  context.fillRect(0, 0, WIDTH, HEIGHT);
  createFood();
  displayFood();
  drawSnake();
}

function clearBoard() {
  context.fillStyle = '#212121';
  context.fillRect(0, 0, WIDTH, HEIGHT);
}

function createFood() {
  foodX = Math.floor(Math.random() * WIDTH / UNIT) * UNIT;
  foodY = Math.floor(Math.random() * HEIGHT / UNIT) * UNIT;
}

function displayFood() {
  context.fillStyle = 'red';
  context.fillRect(foodX, foodY, UNIT, UNIT);
}

function drawSnake() {
  context.fillStyle = 'aqua';
  context.strokeStyle = '#212121';
  snake.forEach(snakePart => {
    context.fillRect(snakePart.x, snakePart.y, UNIT, UNIT);
    context.strokeRect(snakePart.x, snakePart.y, UNIT, UNIT);
  });
}

function moveSnake() {
  const head = { x: snake[0].x + xVel, y: snake[0].y + yVel };
  snake.unshift(head);

  if (snake[0].x == foodX && snake[0].y == foodY) {
    score += 1;
    scoreText.textContent = score;
    createFood();
  } else {
    snake.pop();
  }
}

function nextTick() {
  if (active && !paused) {
    setTimeout(() => {
      clearBoard();
      displayFood();
      moveSnake();
      drawSnake();
      checkGameOver();
      nextTick();
    }, 200);
  } else if (!active) {
    clearBoard();
    context.font = "bold 50px serif";
    context.fillStyle = "white";
    context.textAlign = "center";
    context.fillText("Game Over!!", WIDTH / 2, HEIGHT / 2);
  }
}

function keyPress(event) {
  if (!started) {
    started = true;
    nextTick();
  }

  // Pause/Resume
  if (event.keyCode === 32) {
    paused = !paused;
    if (!paused) nextTick();
  }

  const LEFT = 37, UP = 38, RIGHT = 39, DOWN = 40;
  switch (true) {
    case (event.keyCode == LEFT && xVel != UNIT):
      xVel = -UNIT; yVel = 0;
      break;
    case (event.keyCode == RIGHT && xVel != -UNIT):
      xVel = UNIT; yVel = 0;
      break;
    case (event.keyCode == UP && yVel != UNIT):
      xVel = 0; yVel = -UNIT;
      break;
    case (event.keyCode == DOWN && yVel != -UNIT):
      xVel = 0; yVel = UNIT;
      break;
  }
}

function checkGameOver() {
  switch (true) {
    case (snake[0].x < 0):
    case (snake[0].x >= WIDTH):
    case (snake[0].y < 0):
    case (snake[0].y >= HEIGHT):
      active = false;
      break;
  }

  // Collision with self
  for (let i = 1; i < snake.length; i++) {
    if (snake[i].x == snake[0].x && snake[i].y == snake[0].y) {
      active = false;
    }
  }
}
```

---


---
