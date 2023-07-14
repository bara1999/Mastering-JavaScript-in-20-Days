
# Day 8: JavaScript the Hard Parts

## Lesson Summary
### Asynchronous JavaScript & the event loop
setTimeout  is asynchronous function takes two arguments: the function it will run asynchronously, and the amount of time it will wait before calling that function

Promises act as a placeholder for the data we expect to get back from the web browser feature’s background work


## Coding Examples

```javascript
function printHello(){
 console.log("Hello");
}
setTimeout(printHello,1000);
console.log("Me first!");

//Me first
//Hello

```


## Coding Exercises
### [1st Q](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day2-tasks/tasks.md)

```javascript
const task1 = (cb) => setTimeout(() => {
    const message = "Task 1 has executed successfully!";
    cb(message);
  }, 3000)
  
  const task2 = (cb) => setTimeout(() => {
    const message = "Task 2 has executed successfully!";
    cb(message);
  }, 0)
  
  const task3 = (cb) => setTimeout(() => {
    const message = "Task 3 has executed successfully!";
    cb(message);
  }, 1000)
  
  const task4 = (cb) => setTimeout(() => {
    const message = "Task 4 has executed successfully!";
    cb(message);
  }, 2000)
  
  const task5 = (cb) => setTimeout(() => {
    const message = "Task 5 has executed successfully!";
    cb(message);
  }, 4000)
  
  const asyncTasks = [task1, task2, task3, task4, task5];
  
  const executeInSequenceWithCBs = (tasks, callback) => {
    const res = []
    ca=(r)=>{
        res.push(r);
        if(res.length===tasks.length)
        {
            callback(res);
        }
    };

    tasks.forEach(task => task(ca));
  }
////////////////       Q2       /////////////////////////////////



const apis = [
    {
      apiName: "products", 
      apiUrl: "https://dummyjson.com/products",
    }, 
    {
      apiName: "users", 
      apiUrl: "https://dummyjson.com/users",
    }, 
    {
      apiName: "posts", 
      apiUrl: "https://dummyjson.com/posts",
    }, 
    {
      apiName: "comments", 
      apiUrl: "https://dummyjson.com/comments",
    }
  ]
  
const executeInParallelWithPromises = (apis) => {
    const promises = apis.map(api => {
     const futureData = fetch(api.apiUrl);
      return futureData.then(response => response.json())
        .then(data => {
          return {
            apiName: api.apiName,
            apiUrl: api.apiUrl,
            apiData: data
          };
        });
    });
  
    return new Promise((resolve, reject) =>{
        const arr = [];
        promises.forEach(promise=>{
            promise.then(results => {
                arr.push(results);
                if(arr.length === apis.length)
                resolve(arr)
            }) 
        })
  
    })
  };

  executeInParallelWithPromises(apis).then((r)=>console.log(r))
//////////////////////Q3///////////////////////////
const apis = [
    {
      apiName: "products", 
      apiUrl: "https://dummyjson.com/products",
    }, 
    {
      apiName: "users", 
      apiUrl: "https://dummyjson.com/users",
    }, 
    {
      apiName: "posts", 
      apiUrl: "https://dummyjson.com/posts",
    }, 
    {
      apiName: "comments", 
      apiUrl: "https://dummyjson.com/comments",
    }
  ]
  
const executeInParallelWithPromises = (apis) => {
    const promises = apis.map(api => {
     const futureData = fetch(api.apiUrl);
      return futureData.then(response => response.json())
        .then(data => {
          return {
            apiName: api.apiName,
            apiUrl: api.apiUrl,
            apiData: data
          };
        });
    });
  
    return new Promise((resolve, reject) =>{
        const arr = [];
        promises.forEach(async (promise)=>{
            const d = await promise
            arr.push(d);
            if(arr.length === apis.length)
                resolve(arr)

            // promise.then(results => {
            //     arr.push(results);
            //     if(arr.length === apis.length)
            //     resolve(arr)
            // }) 
        })
  
    })
  };

  executeInParallelWithPromises(apis).then((r)=>console.log(r))
//////////Q3
const apis = [
    {
      apiName: "products", 
      apiUrl: "https://dummyjson.com/products",
    }, 
    {
      apiName: "users", 
      apiUrl: "https://dummyjson.com/users",
    }, 
    {
      apiName: "posts", 
      apiUrl: "https://dummyjson.com/posts",
    }, 
    {
      apiName: "comments", 
      apiUrl: "https://dummyjson.com/comments",
    }
  ]
  
  const executeInSequenceWithPromises = (apis) => {
    const results = [];
  
    const executeNext = async (index) => {
      if (index == apis.length) {
        return results;
      }
  
      const api = apis[index];
  
      try {
        const response = await fetch(api.apiUrl);
        const data = await response.json();
  
        const result = {
          apiName: api.apiName,
          apiUrl: api.apiUrl,
          apiData: data
        };
  
        results.push(result);
  
        return executeNext(index + 1);
      } catch (error) {
        throw new Error(`Error fetching data for API ${api.apiName}: ${error.message}`);
      }
    };
  
    return executeNext(0);
  };

```

