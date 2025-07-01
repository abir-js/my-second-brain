---
tags:
  - nodejs
status: 🟨
---

2025-06-19        21:16

### 🧠 What is the **Module Function Wrapper** in Node.js?

In Node.js, every file is treated as a **module**, and Node **wraps your code** in a function before executing it. This is called the **Module Function Wrapper** (or **Module Wrapper Function**).

---

## 🧩 What it looks like

Internally, Node.js wraps your module code like this:

```js
(function(exports, require, module, __filename, __dirname) {
  // Your actual code goes here
});
```

This is done automatically by Node **before your code runs**.

---

### ✅ Why does Node.js use this wrapper?

It provides **scoping and modularity**. It gives every module:

|Parameter|Description|
|---|---|
|`exports`|Shortcut to `module.exports`|
|`require`|To import other modules|
|`module`|Current module object|
|`__filename`|Absolute path of the current file|
|`__dirname`|Absolute path of the current folder|

---

### 📦 Example

```js
// hello.js
console.log(__filename);  // Full path of this file
console.log(__dirname);   // Folder path

module.exports = function () {
  console.log("Hello from module");
};
```

Before executing, Node wraps it like:

```js
(function(exports, require, module, __filename, __dirname) {
  // console.log(__filename);
  // console.log(__dirname);
  // module.exports = function () { ... };
});
```

---

### 🔐 Benefit: Private Scope

Variables in one file don't pollute the global scope:

```js
let secret = 'hidden';
// Not accessible in other modules
```

---

## 🧵 Summary

- Node wraps each module in a function before running it.
    
- This gives every file a **private scope** and access to helpful variables.
    
- That’s why `require`, `module`, etc., work in every file **without imports**.
    

Let me know if you want to simulate the wrapper or see how it behaves in REPL!

## Related topics: 

- 

## References

