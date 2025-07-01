
2025-06-17 10:13

Status: 

Tags: #javascript 

Related topics:   [[lexical scope]] 

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

## References

- [[lexical scope]]
