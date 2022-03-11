## Javascript_notes


## Variables & Constants 
A "data container"/"data storage"
```javascript
let userName='Ten'; 
userName = "Eleven";
```

// A Data contianer / Data Storag ,  Where the value must not change!

```javascript
const totalUsers = 10;
totalUsers = 13; 
```

## Variable Naming allowed 

```javascript
let userName // camelCase 
let ageGroup5 // only letter and digits 
let $kindOfSpecial // starting with $ is allowed 
let _internalValue  //starting with _ is allowed 
```

## Not Allowed 

```javascript
let user_name // is bad practice 
let 21Players // starting digits not allowed 
let user-b // No special characters!
let let  //keyword not allowed 
```

## Data Types 

Numbers 2, -3, 22.956 

String(Text) 
```javascript
//String types 
'Hi' 
"Hi"
`Hi`
```

## Functions 

```javascript
function greetUser(name) {
    alert('Hi' + name)
}
// Run as many time as we call  function 
// Runs indepent of other executions 

function sum(x, y) {
    return x + y;
}
//This piece of code defines a function called sum.
function sum(x, y) {
    return x + y;
    console.log("Hello World"); // this will NEVER run
}
//The return keyword will quit the function with the result (which is x + y), so the code afterward will never run!
----------------------*--------------------------
// Parameters are essentially passed to functions by value — so if the code within the body of a function assigns a completely new value to a parameter that was passed to the function, the change is not reflected globally or in the code which called that function.

function myFunc(theObject) {
  theObject.make = 'Toyota';
}

var mycar = {make: 'Honda', model: 'Accord', year: 1998};
var x, y;

x = mycar.make; // x gets the value "Honda"

myFunc(mycar);
y = mycar.make; // y gets the value "Toyota"
                // (the make property was changed by the function)


// While the function declaration above is syntactically a statement, functions can also be created by a function expression.

const square = function(number) { return number * number }
var x = square(4) // x gets the value 16


const factorial = function fac(n) { return n < 2 ? 1 : n * fac(n - 1) }

console.log(factorial(3))

```




## Arrays 


Arrays are generally described as "list-like objects"; they are basically single objects that contain multiple values stored in a list. 




```javascript

// Arrays consist of square brackets and items that are separated by commas.

const grocessories = []; //empty array 
const shopping = ['bread', 'milk', 'cheese', 'hummus', 'noodles'];
console.log(shopping);

//array we can store various data types — strings, numbers, objects, and even other arrays
const sequence = [1, 1, 2, 3, 5, 8, 13];
const random = ['tree', 795, [0, 1, 2]];


const shopping = ['bread', 'milk', 'cheese', 'hummus', 'noodles'];
console.log(shopping.length);  // 5
console.log(shopping[0]);  // returns "bread"

// Modify an item in an Array 
shopping[0] = 'tahini';
console.log(shopping);
// shopping will now return [ "tahini", "milk", "cheese", "hummus", "noodles" ]
```

Note that an array inside an array is called a multidimensional array. You can access an item inside an array that is itself inside another array by chaining two sets of square brackets together.

```javascript
const random = ['tree', 795, [0, 1, 2]];
random[2][2]; 
```

Other functions in Arrays 

```javascript
// Finding items in Array

//indexOf() 
//push()
//unshift() = Add element to start of the array use unshift()
//pop() = To remove the last item from the array, use pop()
//shift() = To remove the first item from an array, use shift()
// splice() = If you know the index of an item, you can remove it from the array using splice()

const birds = ['Parrot', 'Falcon', 'Owl'];
console.log(birds.indexOf('Owl'));   //  2
console.log(birds.indexOf('Rabbit')); // -1

// To add one or more elements 
const cities = ['HYD', 'Banglore'];
cities.push('Chennai');
console.log(cities);      // [ "HYD", "Banglore", "Chennai" ]
cities.push('Vizag', 'Mumbai');
console.log(cities);      // [ "HYD", "Banglore", "Chennai", "Vizag", "Mumbai" ]


// Add element to start of the array use unshift()
const cities = ['HYD', 'Banglore'];
cities.unshift('Chennai');
console.log(cities); // [ "Chennai","HYD", "Banglore"]

//Remove using pop 
const cities = ['HYD', 'Banglore'];
cities.pop();
console.log(cities); // [ "HYD"]

const cities = ['HYD', 'Banglore', 'Chennai'];
const index = cities.indexOf('Banglore');
if (index !== -1) {
  cities.splice(index, 1);
}
console.log(cities);  // [ "HYD","Chennai"]
```



All  Array Functions

```javascript 

Array Functions

[1,2,3].push(4) // [1,2,3,4]
[1,2,3].pop() // [1,2]
[1,2,3].shift() //[2,3]
[1,2,3].unshift() // [0,1,2,3]
['a','b'].concat('c') //['a','b','c']
['a','b','c'].join('-') // a-b-c
['a','b','c'].slice(1) // ['a','b']
['a','b','c'].indexOf('b') //1 
;['a','b','c'].includes('c') //true 

[3,5,6,8].find((n) => n %2  === 0 ) // 6 
[2,4,3,5].findIndex((n) => n %2!== 0) // 2 
[3,4,8,6].map((n)=> n * 2) // [6,8,16,12]
[1,4,7,8].filter((n) => n % 2 === 0) // [4,8]
[2,4,3,7].reduce((acc,cur) => acc + cur) // 16 
[2,3,4,5].every((x) => x < 6) // true 
[3,5,6,8].some((n) => n > 6) // true
[1,2,3,4].reverse() // [4,3,2,1]
[3,5,7,8].at(-2) //7

```



Above code reference from below link 
https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays

## Objects 

JavaScript is designed on a simple object-based paradigm. An object is a collection of properties, and a property is an association between a name (or key) and a value. 

Like all JavaScript variables, both the object name (which could be a normal variable) and property name are case sensitive.

```javascript
const myCar = new Object();
myCar.make = 'Ford';
myCar.model = 'Mustang';
myCar.year = 1969;

//Object initializer

```

Objects can be initialized using new Object(), Object.create() or using the literal notation (initializer notation). 

```javascript
const object1 = { a: 'foo', b: 42, c: {} };

console.log(object1.a);
// expected output: "foo"

const a = 'foo';
const b = 42;
const c = {};
const object2 = { a: a, b: b, c: c };

console.log(object2.b);
// expected output: 42

const object3 = { a, b, c };

console.log(object3.a);
// expected output: "foo"

//Output
"foo"
42
"foo"


// four variables are created and assigned in a single go,
// separated by commas
const myObj = new Object(),
      str = 'myString',
      rand = Math.random(),
      obj = new Object();

myObj.type              = 'Dot syntax';
myObj['date created']   = 'String with space';
myObj[str]              = 'String value';
myObj[rand]             = 'Random Number';
myObj[obj]              = 'Object';
myObj['']               = 'Even an empty string';

console.log(myObj);

```

Above code reference from below link 
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects




## Debug Javascript
Tutorial will help wiht DevTools debugging
https://developer.chrome.com/docs/devtools/javascript/




## ES6 or ECMAScript 6 
ES6 Refer to: https://medium.com/geekculture/modern-javascript-25cce3e5af8f

ES6 in simple Terms 
https://github.com/imalitavakoli/learn-es6



## Reference Below Links 
https://github.com/GitbookIO/javascript (Better Explanation of functions, Objects and Arrays ...)
https://github.com/airbnb/javascript
https://github.com/wesbos/JavaScript30
MDN => JavaScript Basics: https://developer.mozilla.org/en-US/docs/Web/JavaScript

MDN => Variables: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Variables

MDN => Operators: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Math

MDN => Functions: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Functions

MDN => Arrays: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays

MDN => Objects: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics

## Interview Related
https://github.com/lydiahallie/javascript-questions
https://github.com/TheAlgorithms/Javascript

## Additional 
https://github.com/sorrycc/awesome-javascript
https://github.com/ryanmcdermott/clean-code-javascript
https://forum.freecodecamp.org/


## ECMAScript 6 Tools 
https://github.com/addyosmani/es6-tools#readme


## Algorithms 

https://github.com/prasanna16-12/Sorting-Algorithm-Visualizer



