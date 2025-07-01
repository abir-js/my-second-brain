
2025-06-17 13:42

Status: 

Tags: #javascript #js-interview-questions 

Related topics:   [[global execution context]]

# What is Function Execution Context?

Just as [[global execution context]], a function execution context gets created in [[global execution context#Code Phase|Code Phase]] of [[global execution context]].

```js
console.log("Global Execution Context Starts");

var globalVariable = "I am a global variable";

function globalFunction() {
  console.log("Inside global function");
}

console.log(globalVariable);
globalFunction();

console.log("Global Execution Context Ends");
```

![[function-execution-context.png]]

After that function execution context and [[global execution context]] will get deleted from [[call stack]].

![[function-execution-context-scope.png]]
## References



