---
tags:
  - javascript
  - js-interview-questions
status: 🟩
---

2025-07-17        10:13

Related topics:   [[lexical scope]] 

---
# What is closure?

A closure is the combination of a function bundled together (enclosed) with references to its surrounding state ( [[lexical scope|lexical environment]] ).

```js
function stepCounter(stepSize = 1, initialStep = 0) {
  return function () {
    initialStep = stepSize + initialStep;
    return initialStep;
  };
}

let step = stepCounter(10, 5);
console.log(step());
console.log(step());
console.log(step());
console.log(step());
```

---

## Closure in react

> A closure is a feature in JavaScript where inner function has access to the outer (enclosing) function's variables.

```jsx
function outer(){
	let a = 10;
	function inner() {
		let b = 20;
		console.log(a + b);
	}
	return inner;
}
```

---
## References

- [[lexical scope]]
