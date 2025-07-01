
2025-06-17 12:22

Status: 

Tags: #javascript #js-interview-questions 

Related topics:   [[function execution context]] 

# What is Global Execution Context?

Whenever you runs a js code, a global execution context gets created in [[call stack]].

There are two phases of GEC -
- Memory Phase
- Code Phase

## Memory Phase

Every variables are loaded in memory phase with **initial value undefined** because of [[hoisting]]. Also functions with its full body gets [[hoisting|hoisted]].

## Code Phase

In code phase, all values gets initialized in memory phase and rest of the code gets executed.

Code phase main sare values initialize ho jate hai memory phase ke variables mei. Or baki code execute ho jate hai.

```js
console.log("value of x is: ", x); //value of x is undefined
var x = 10;
```


![[global-execution-context-var-example.png]]

```js
console.log("value of x is: ", x); // TypeError: Can't access x before initialization
let x = 10;
```

Ak bar run ho jane ke baad pura execution context delete ho jata hai.

## References

[[hoisting]]

