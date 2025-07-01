---
tags:
  - nodejs
status: 🟩
---

2025-06-20        20:28

# ✅ What is an ES Module?

**ES Module (ECMAScript Module)** is the official standard format to organize and share JavaScript code across files in **modern JavaScript (ES6 and later)**.
Available since **version 12**.


> [!IMPORTANT] Title
> After Node.js version 14.8, you can use top level await.


---

### 📦 Key Concepts:

|Feature|Description|
|---|---|
|`export`|Used to expose variables, functions, classes from a module|
|`import`|Used to bring in functionality from another module|
|File Extension|Typically `.mjs` or `.js` with `"type": "module"` in `package.json`|
|Static Structure|Imports/exports must be at the top level — can't be dynamic|

---
### 🆚 ES Module vs CommonJS

|Feature|ES Module (`import/export`)|CommonJS (`require/module.exports`)|
|---|---|---|
|Syntax|`import`, `export`|`require`, `module.exports`|
|Loading|Static (at parse time)|Dynamic (at runtime)|
|File Ext|`.js` (with `"type": "module"`) or `.mjs`|`.js`|
|Interop|Supported but tricky|Legacy standard|

---
### 🔁 Default Export:

- We can only share one item. It can be a variable or an object
-  We can use any name in import file

#### `math.js` – exporting:

```js
const add = (a, b) => a + b;
export default add;
```

#### `main.js` – importing:

```js
import sum from "./math.js";
console.log(sum(5, 2));
```

---

### 🔁 Named Export:

- We have to use { } during import
- Have to use same name
- We can export multiple items

#### `math.js` – exporting:

```js
export const sub = (a, b) => a - b;
export const mul = (a, b) => a * b;
```

#### `main.js` – importing:

```js
import { sub, mul } from "./math.js";
console.log(sub(5, 2))
console.log(mul(5, 2))
```

---

### 🔁 Export All Items:

#### `math.js` – exporting:

```js
const div = (a, b) => a / b;
const PI = 3.142

export {div, PI}
```

#### `main.js` – importing:

```js
import {div, PI} from "./math.js"
console.log(div(5, 2))
console.log(PI)

// or
import * as math from "./math.js"
console.log(math.div(5, 2))
console.log(math.PI)
```

---


### 🔄 Named vs Default Export:

|Type|Syntax|Import|
|---|---|---|
|Named|`export const a = 1`|`import { a } from './file.js'`|
|Default|`export default a`|`import a from './file.js'`|

---

### ⚙️ Using ES Modules in Node.js

To enable ES Modules in Node.js:

1. Use `.mjs` extension **OR**
    
2. Add `"type": "module"` in `package.json`
    

```json
// package.json
{
  "type": "module"
}
```

Now you can use:

```js
import fs from 'fs/promises';
```

---

### ❗ Things You Can’t Do in ES Modules:

- No `require()` or `module.exports`
    
- No top-level `await` (unless in recent versions with module support)
    
- Imports are **hoisted** and must be **static** (no dynamic paths)
    


---

## Related topics: 

- 

---


