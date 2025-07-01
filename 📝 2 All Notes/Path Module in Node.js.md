---
tags:
  - nodejs
status: 🟥
---

2025-06-18        23:57

# What is Path Module in Node.js?

In Node.js, the path module provides utilities for working with file and directory paths. It's  a built-in module, so you don't need to install any external packages.

# Note - *Only available in CommonJS*

👉 Check -  [[Double-backslash problem in windows with path module]]

###  __ filename:

- Provides absolute path of the currently executing file.

###  __ dirname:

- Provides absolute directory path of currently executing file.

```js
const path = require("path")

console.log(__dirname) // F:\coding\NodeJS\ThapaTechnical\8-path-module
console.log(__filename) // F:\coding\NodeJS\ThapaTechnical\8-path-module\path_module.js  
```

## Methods:

### 1. path.parse(): 

Returns an object with details about current path, including root, dir, base, ext and name.

```js
const path = require("path")

const newPath = path.join("folder", "students", "data.txt")
console.log(path.parse(newPath));  // folder\students\data.txt
/*{
  root: '',
  dir: 'folder\\students',
  base: 'data.txt',
  ext: '.txt',
  name: 'data'
}*/
```
### 2. path.join():

Joins multiple path segments into one, using the  appropriate separator ( \ in windows, / in MacOS and Linux )

```js
// Create a file path folders/students/data.txt
const path = require("path");

const newPath = path.join("folder", "students", "data.txt")
console.log(newPath);  // folder\students\data.txt
```
### 3. path.resolve()

Resolves sequence of paths into an absolute path, starting from the current directory.

```js
const path = require("path")

const newPath = path.join("folder", "students", "data.txt")
console.log(path.resolve(newPath)); // C:\Users\hp\coding\NodeJS\ThapaTechnical\folder\students\data.txt
```

### 4. path.extname():

Extracts file extension from given path
### 5. path.basename()

Returns the last part of a path ( e.g. file name with extension )
### 6. path.dirname():

Returns directory part of a path
### 7. path.sep:

returns the platform-specific path segment separator ( \ for Windows, / for Linux/MacOS )
## Related topics: 

- [[Double-backslash problem in windows with path module]]

## References

