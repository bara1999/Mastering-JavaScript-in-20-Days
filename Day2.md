
# Day 2: Basic JavaScript

## Lesson Summary

###  Expression & values
Expressionis a valid unit of code that resolves to a value.
To declaring a variable we can use let or const.

### Arrays
Arrays let us keep multiple values together in a single collection.
There are some methods in arrays like string for example: length, indexof,etc.
The pop() method removes (pops) the last element of an array.
The push() method adds new items to the end of an array.
The join() method returns an array as a string.
The concat() method concatenates (joins) two or more arrays.

### Objects
Objects collect multiple values together to describe more complex data.
objects let us point at related values using properties in the object.
this in a method lets us reference other properties on the object.
Nested objects is object of object.


## Coding Examples

```javascript
let scrub = "guy that thinks he's fly";
let busta = scrub;
scrub = "guy that can't get no love from me";

//Example on array
let synonyms = ["plethora", "array", "cornucopia"];
consol.log(synonyms.length);
consol.log(synonyms[1]);
consol.log(synonyms.indexOf("cornucopia"));
synonyms[1] = "variety";
let lastItem = synonyms.pop();
synonyms.push("multitude");
let cArray=[1, 2, 3].concat([4, 5, 6]);
let jArray=["lions", "tigers", "bears oh my!"].join(" & ");


//Example on object
const dog = {
    name: "Ein",
    breed: "Corgi",
    speak: function () {
        console.log("woof woof");
    }
}
anjana.speak = function () {
    console.log("Hi my name is", this.name);
}
anjana.speak();



```


## Coding Exercises

### [Profile Lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)

### [Profile Lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)

### [Profile Lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)


#### My Solution


```javascript
// Setup
const contacts = [
  {
    firstName: "Akira",
    lastName: "Laine",
    number: "0543236543",
    likes: ["Pizza", "Coding", "Brownie Points"],
  },
  {
    firstName: "Harry",
    lastName: "Potter",
    number: "0994372684",
    likes: ["Hogwarts", "Magic", "Hagrid"],
  },
  {
    firstName: "Sherlock",
    lastName: "Holmes",
    number: "0487345643",
    likes: ["Intriguing Cases", "Violin"],
  },
  {
    firstName: "Kristian",
    lastName: "Vos",
    number: "unknown",
    likes: ["JavaScript", "Gaming", "Foxes"],
  },
];

function lookUpProfile(name, prop) {
  for(let i=0;i<contacts.length;i++)
  {
     if (contacts[i].firstName === name) {
      if (prop in contacts[i]) {
        return contacts[i][prop];
      } else {
        return "No such property";
      }
    }
   
   
    
  }
   
     return "No such contact";
    


}

lookUpProfile("Akira", "likes");

```
### [Copy Array Items Using slice()](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/copy-array-items-using-slice)

#### My Solution


```javascript
function forecast(arr) {


arr= arr.slice(2, 4);
  return arr;
}


console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));
```
### [Combine Arrays with the Spread Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/combine-arrays-with-the-spread-operator)

#### My Solution


```javascript
function spreadOut() {
  let fragment = ['to', 'code'];
  let sentence=['learning',...fragment,'is', 'fun']; // Change this line
  return sentence;
}

console.log(spreadOut());

```