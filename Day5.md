
# Day 5: Basic JavaScript

## Lesson Summary
### Fetching data
APIs provide URLs that point at data we care about.
fetch() uses to load data from APIs.

### Promises
Promises can be in 3 possible states:
pending: still waiting for the value, hang tight .
resolved: finally got the value, all done.
rejected: sorry couldn't get the value, all done.
It takes time for Promises to resolve, so they are "asynchronous".

await method tell JS to stop and wait for an asynchronous operation to finish.


### Destructuring
Destructuring is a fancy way of declaring multiple variables at once.
Destructure Arrays is assigning variables for their items.
Commas use to "skip" values.



### Map & Filter
map calls a function on each item in an array to create a new array.
filter calls a true/false function on each item and creates a new array with only the items where the function returns true.



## Coding Examples

```javascript
let response = await fetch("https://dog.ceo/api/breed/hound/list");
console.log(response);

//Destructuring
const spices = [
    {name: "Emma", nickname: "Baby"},
    {name: "Geri", nickname: "Ginger"},
    {name: "Mel B", nickname: "Scary"},
    {name: "Mel C", nickname: "Sporty"},
    {name: "Victoria", nickname: "Posh"}
];
let {name, nickname} = spices[0];
const [baby, ginger, scary, sporty, posh] = spices;
const [,,melB] = spices;
const [babySpice, ...adultSpices] = spices;//"..." we use this  to collect remaining values

```


## Coding Exercises

### [fetching data ](https://github.com/bara1999/day5)


