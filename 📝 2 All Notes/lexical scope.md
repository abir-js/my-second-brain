---
tags:
  - javascript
  - js-interview-questions
status: 🟩
---

2025-06-18 14:57

# What is lexical scope?

Lexical scope in JavaScript determines variable accessibility based on where the function is written in the code. It is also known as static scope. This means that a function has access to variables in its parent scope, even if the parent function has already finished executing.

```js
function createCounter() {
  let count = 10;
  // Closure - Function binded by its lexical scope
  return function () {
    count++;
    return count;
  };
}

let f  = createCounter()
console.log(f());
console.log(f());
console.log(f());
let g  = createCounter()
console.log(g());
console.log(g());
console.log(g());
```



## Related topics: 

- [[closure]]


