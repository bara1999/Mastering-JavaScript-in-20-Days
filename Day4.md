
# Day 4: Basic JavaScript

## Lesson Summary
### Events & Handlers
The web browser fires events when certain things happen on the page.
The .addEventListener() method lets us listen for events on a DOM element.

### Conditionals
code in the if block only runs if the (condition) is true, we use else to run other code if (condition) is false.
The ! operator negates a boolean.
Logical "and" (&&) requires both values to be truthy.
Logical "or" (||) requires only one value to be truthy.

### Loops
Loops are handy, if you want to run the same code over and over again, each time with a different value.

JavaScript supports different kinds of loops:
for - loops through a block of code a number of times
for/of - loops through the values of an iterable object
while - loops through a block of code while a specified condition is true

### Map & Filter
map calls a function on each item in an array to create a new array.
filter calls a true/false function on each item and creates a new array with only the items where the function returns true.



## Coding Examples

```javascript
//event
document.addEventListener("click", () => {
    console.log("clicked")
});
//conditional
if (0) {
    console.log("zero is truthy");
} else {
    console.log("zero is falsy");
}
//lppos
const numbers = [1,2,3];
for (let i = 0; i < numbers.length; i++) {
    console.log(numbers[i]);
}
for (let n of numbers) {
    console.log(n);
}

//filter & map
const spices = [
    {name: "Emma", nickname: "Baby"},
    {name: "Geri", nickname: "Ginger"},
    {name: "Mel B", nickname: "Scary"},
    {name: "Mel C", nickname: "Sporty"},
    {name: "Victoria", nickname: "Posh"}
];
const nicknames = spices.map(s => s.nickname + " Spice");
const mels = spices.filter(s => s.name.includes("Mel"));
```


## Coding Exercises

### [Use Multiple Conditional (Ternary) Operators](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-multiple-conditional-ternary-operators)


#### My Solution


```javascript
function checkSign(num) {
   return (num>0) ? "positive" 
    : (num<0) ? "negative" 
    : "zero";

}

checkSign(10);
```
### [Golf Code](hhttps://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/golf-code)

#### My Solution


```javascript
/const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  // Only change code below this line
if(strokes==1)
return "Hole-in-one!";
else if(strokes<= par - 2)
return "Eagle";
else if(strokes==par - 1)
return "Birdie";
else if(strokes==par)
return "Par";
else if(strokes==par + 1)
return "Bogey";
else if(strokes==par + 2)
return "Double Bogey";
else if(strokes>=par + 3)
return "Go Home!";

  return "Change Me";
  // Only change code above this line
}

golfScore(5, 4);
```

### [Use the map Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-map-method-to-extract-data-from-an-array)

#### My Solution


```javascript

// Only change code below this line

const ratings =  watchList.map(i => ({title: i.Title , rating :i.imdbRating}));

// Only change code above this line

console.log(JSON.stringify(ratings));
```

### [Use the filter Method to Extract Data from an Array](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-the-filter-method-to-extract-data-from-an-array)

#### My Solution


```javascript
const filteredList = watchList.map(i => ({title: i.Title , rating :i.imdbRating})).filter(i => (+i.rating) >=8);
console.log(filteredList);
```