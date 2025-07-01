---
tags:
  - nodejs
status: 🟩
---

2025-06-18        21:26

# What is Title?

CommonJS is a module system specification primarily used in JavaScript, especially in environments like Node.js.

### What is CommonJS?

- **CommonJS** defines a standard for how JavaScript modules should be written and loaded.
    
- It allows you to **export** code from one file and **import** it in another, enabling modular programming.
    
- CommonJS modules are loaded **synchronously**, which works well for server-side environments like Node.js.

### Key Features of CommonJS

- Uses `require()` to **import** modules.
    
- Uses `module.exports` or `exports` to **export** functionality.
    
- Modules are loaded synchronously.
    
- Mainly used in **Node.js** but less used in browsers because synchronous loading is not efficient in browsers.
    

### Example

**module1.js** (exporting)

```js
function greet(name) {
	return `Hello, ${name}!`; 
}  
module.exports = greet;
```

**app.js** (importing)

```js
const greet = require('./module1');  
console.log(greet('Abir')); // Output: Hello, Abir!
```

---

### Comparison to ES Modules

- CommonJS uses `require` and `module.exports`.
    
- ES Modules (ESM) use `import` and `export` syntax and support asynchronous loading.
    
- Browsers now mostly use ES Modules, but Node.js supports both.

## Related topics: 

- 

## References

