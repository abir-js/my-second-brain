---
tags:
  - nodejs
status: 🟩
---

2025-06-18        21:45

# What are problems with module.exports?

`module.exports` is a single object or value. When you re-assign `module.exports`, it completely replaces whatever has previously assigned.

**In math.js:** 

```js
const add = (a, b) => a + b;
const sub = (a, b) => a - b;

module.exports = add;
module.exports = sub;
```

**In app.js:** 

```js
// CommonJS
const add = require("./math")
const sub = require("./math")
console.log(add(2, 3)); // -1
console.log(sub(2, 3)); // -1
```

### How to avoid

- use { } in `module.exports`

```js
module.exports = { add, sub}
```

- use `module.exports.property`

**In math.js:** 

```js
module.exports.add = add;
module.exports.sub = sub;
```

**In app.js:**

```js
const {add, sub} = require("./math");
// or
const math = require("./math");
console.log(math.add(2, 5));
```


## Related topics: 

- 

## References

