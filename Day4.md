
# Day 1: Basic JavaScript

## Lesson Summary



## Coding Examples

```javascript

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