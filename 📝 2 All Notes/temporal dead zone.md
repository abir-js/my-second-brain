
2025-06-17 15:44

Status: 

Tags: #javascript   #js-interview-questions 

Related topics:  [[hoisting]]

# What is temporal Dead Zone?

The term "temporal dead zone" (TDZ) refers to a specific period in JavaScript code execution related to variables declared with `let` and `const`. It's the time between the start of a scope (like a block or function) and when the variable is actually declared and initialized. 

During the TDZ, the variable exists but is inaccessible. Attempting to access it before its declaration results in a `ReferenceError`. This behavior differs from `var` declarations, which are hoisted and initialized with `undefined` even before the declaration line. 

The TDZ helps to catch errors by preventing access to variables before they are properly set up. It also ensures more predictable behavior for `const` variables, which must be initialized upon declaration.

The "temporal" aspect emphasizes that the zone's duration depends on execution order rather than the code's physical layout.

```js
x = 30;
console.log("Value of x is: ", x); // Error
let x = 10;
console.log("Value of x is: ", x); // 10
```

![[Excalidraw/Temporal Dead Zone|Temporal Dead Zone]]

Here, we can't access x before it's initialization. But, x gets hoisted. We can verify it using error message or debugger. 

## References


