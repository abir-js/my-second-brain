---
tags:
  - nodejs
status: 🟩
---

2025-06-18        20:33

# What are modules in Node.JS?

- A module in Node.js represents a file containing code that is self-contained reusable, and encapsulated

- Node.js uses [[CommonJS]] module system.

### example:

**In math.js:** 

```js
function add(a, b) {
  return a + b;
}
module.exports = add;
```

**In app.js:** 

```js
// CommonJS
const add = require("./math")
console.log(add(2, 3));
```

### Self-contained code unit:

- Each file in Node.js is treated as a separate module.
- Variables, functions or objects are not accessible in another file system if you don't explicitly export them.

### Encapsulation:

- Node.JS used CommonJS (`module.exports` and `require`) to ensure code in one file doesn't interfere with global scope.

## Related topics: 

1. [[Node.js internals]]
2. [[CommonJS]]
3. [[Module Wrapper Function]]
## References

