
# Day 8: JavaScript the Hard Parts

## Lesson Summary
### Classes, Prototypes - Object Oriented JavaScript
Usin Object-oriented make:
1. Easy to add function
2. Nevertheless efficient and performant
 

Creating object:
1. Creating object with their properties and method.
2. Creating object using dot notation.
3. Creating object using Object.create

All objects have a __proto__ property by default which defaults to linking to a big object - Object.prototype full of (somewhat) useful functions.

Functions are both objects and functions.

Properties in the prototype are shared among ALL instances.

Constructors are functions that create new objects. They define properties and behaviors that will belong to the new object. 

## Coding Examples

```javascript
const user1 = {
 name: "Will",
 score: 3,
 increment: function() { user1.score++; }
};
user1.increment(); //user1.score -> 4

//function as object
function multiplyBy2(num){
 return num*2
}
multiplyBy2.stored = 5
multiplyBy2(3) // 6

//usin constructor
class UserCreator {
 constructor (name, score){
 this.name = name;
 this.score = score;
 }
 increment (){ this.score++; }
 login (){ console.log("login"); }
}
const user1 = new UserCreator("Eva", 9);
user1.increment();

```


## Coding Exercises
### [ Object Oriented Programming](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week2-day4-tasks/tasks.md)

### [My solution](https://www.freecodecamp.org/baraa_alsaeed)
