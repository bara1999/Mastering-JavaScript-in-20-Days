
# Day 6: JavaScript the Hard Parts

## Lesson Summary
### JavaScript principles
1. When JavaScript code runs, it Goes through the code line-by-line and runs each line  known as the thread of execution
2. Functions are Code define the we can call it later with the function’s name & ( ).
3. JavaScript keeps track of what function is currently running and  add it to call stack then when Finish running the function js removes it from call stack.


### Promises
Promises can be in 3 possible states:
pending: still waiting for the value, hang tight .
resolved: finally got the value, all done.
rejected: sorry couldn't get the value, all done.
It takes time for Promises to resolve, so they are "asynchronous".

await method tell JS to stop and wait for an asynchronous operation to finish.
 

### Callbacks & Higher Order Functions
Using function allow to us to (DRU).
higher-order function: The outer function that takes in a function(callback).


## Coding Examples

```javascript
function copyArrayAndManipulate(array, instructions) {
 const output = [];
 for (let i = 0; i < array.length; i++) {
 output.push(instructions(array[i]));
 }
 return output;
}// functin take callback as parameter
const result = copyArrayAndManipulate([1, 2, 3], input => input*2);

```


## Coding Exercises
### [1st Q](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programminguse-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problm)

```javascript
const squareList = arr => {
arr=  arr.filter(i=>(i>0 && Number.isInteger(i)) )
arr=arr.map(i=>i*i)
  return arr;
  // Only change code above this line
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);

```
### [2nd Q](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)

```javascript
function urlSlug(title) {
return title.split(" ").filter(s => s !== "").join("-").toLowerCase();;
    

}
// Only change code above this line
urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone");


```
### [Third Q](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day1-tasks/tasks.md)

```javascript
const mapAsync = (arr,cb)=>{
return new Promise((resolve,reject)=>{

    const a = []
for ( i=0;i<arr.length;i++){
    cb(arr[i]).then((result)=>{
        a.push(result);
        if(a.length===arr.length)
        resolve(a);

    }).catch((err)=>{
        reject(err);

    });
}

})


}
//////////////////////////
const rec=(first,final)=>{

    if(first===final)
    return first;
    return (first+rec(first+i,final));
}
```
