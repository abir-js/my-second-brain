
2025-06-17 15:21

Status:

Tags: #javascript  #js-interview-questions  

Related topics:  
[[global execution context]]
[[function execution context]]
[[temporal dead zone]]  

# What is Hoisting?

Hoisting is a **concept or behavior in JavaScript where the declaration of a function, variable, or class goes to the top scope where they were defined in.**

```js
x = 30;
console.log("Value of x is: ", x); // 30
var x = 10;
console.log("Value of x is: ", x); // 10
```

```js
x = 30;
console.log("Value of x is: ", x); // Error
let x = 10;
console.log("Value of x is: ", x); // 10
```

## Is let, const gets hoisted as var?

Yes let and const also gets gets hoisted but we can't access the variables because of [[temporal dead zone]].
## References

[[temporal dead zone]]





