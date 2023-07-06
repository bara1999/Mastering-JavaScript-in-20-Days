
# Day 3: Basic JavaScript

## Lesson Summary

### Functions:
we learnt declaring a function and calling it
functions can hold one or more parameters.
parameters are the inputs a function expects.
arguments are the actual values the function is called with.
A return statement specifies the function's output value.

### Arrow Function:
The arrow function  =>  lets us create an unnamed function without much code, we can assign arrow function to a variable.

### Scope
Scope determines where variables are "in play".
The widest scope is the global scope.
Each function gets its own new scope within the scope where it was declared.
Variables declared with the var keyword can NOT have block scope.


## Coding Examples

```javascript
function add3(x, y, z) { //x,y,z are parameters 
    console.log("My parameters are named x, y, z");
    console.log("I received the arguments", x, y, z);
    return x + y + z;
}
const sum = add3(4,5,6); // 4,5,6 are arguments

const add = (x, y) => x + y; //arrow function

function declareBankruptcy() {
    let bankruptcy = true;
}
declareBankruptcy();
console.log(bankruptcy);//this will raise an error.

let planet = "Jupiter";
function scopeOut() {
    let planet = "Mars";
    console.log("Inner planet:", planet);
}
scopeOut();//Inner planet: Mars
console.log("Outer planet:", planet);//Inner planet: Jupiter

let x = 10;
{
let x = 2;
}
consol.log(x);// x is 10

var x = 10;
{
var x = 2;
}
consol.log(x) // x is 2

```


## Coding Exercises

### [Return a Value from a Function with Return](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/return-a-value-from-a-function-with-return)


#### My Solution


```javascript
function timesFive(num) {
  return num *5;
}

const answer = timesFive(5);

```
### [Global Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-scope-and-functions)

#### My Solution


```javascript
// Declare the myGlobal variable below this line
let myGlobal=10;

function fun1() {
  // Assign 5 to oopsGlobal here
 oopsGlobal=5;
}

// Only change code above this line

function fun2() {
  let output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}
```

### [Local Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)

#### My Solution


```javascript
function myLocalScope() {
  // Only change code below this line
let myVar=5;
  console.log('inside myLocalScope', myVar);
}
myLocalScope();

// Run and check the console
// myVar is not defined outside of myLocalScope
console.log('outside myLocalScope', myVar);
```

### [Stand in Line](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line)

#### My Solution


```javascript
function nextInLine(arr, item) {
  // Only change code below this line
  arr.push(item);
  let x = arr.shift();
  return x;
  
  // Only change code above this line
}

// Setup
let testArr = [1, 2, 3, 4, 5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```