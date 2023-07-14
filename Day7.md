
# Day 7: JavaScript the Hard Parts

## Lesson Summary
### Closure
When functions get called, we create a live store of data (local memory) for that function’s execution context , and When the function finishes executing, the local memory is deleted.
A closure is a feature of JavaScript that allows inner functions to access the outer scope of a function.
A closure is a function having access to the parent scope, even after the parent function has closed.



## Coding Examples

```javascript
function outer (){
 let counter = 0;
 function incrementCounter (){ counter ++; }
 return incrementCounter;
}
const myNewFunction = outer();
myNewFunction();
myNewFunction();

```


## Coding Exercises
### [1st Q](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md)

```javascript
const add=(c)=>{
    
    const incremment=()=>{
        c++;
        return c;
    }
    return increment;
}

const myfun=add(0);
consol.log(myfun());//1
consol.log(myfun());//2
/////////////////////////////////////////////////



const calAvg=(nums)=>{
    return ()=>{
       const sum= nums.reduce((sum,num)=>{
         sum+=num;
         return sum;   
        },0)
        return sum/nums.length;

    }
}
const myfun=calAvg([1,2,3]);
consol.log(myfun());//2
/////////////////////////////////////////////////

const power=(b)=>{
    return (e)=>{
       
        return Math.power(b,e);

    }
}
const myfun=power(2);
consol.log(myfun(3));//8

/////////////////////////////

const f=(cb1,cb2,cb3)=>{
    return(x)=>{
        return cb1(cb2(cb3(x)));
    };
}
function add2(x) {
  return x + 2;
}

function multiply3(x) {
  return x * 3;
}

function subtract5(x) {
  return x - 5;
}
const myfun=f(add2,multiply3,subtract5);
consol.log(myfun(3));//-4
```

