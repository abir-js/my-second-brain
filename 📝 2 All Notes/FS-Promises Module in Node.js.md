---
tags:
  - nodejs
status: 🟩
---

2025-06-19        15:59

# 📂 Node.js `fs/promises` Module

The `fs/promises` API in Node.js provides **Promise-based** versions of the `fs` (file system) methods. It enables modern **async/await** syntax for file operations.

> Introduced in Node.js **v10+**, stable in **v14+**

---

## ✅ Importing `fs/promises`

```js
const fs = require('fs/promises');
```

Or with ES Modules:

```js
import * as fs from 'fs/promises';
```

---

## 🔹 Common `fs/promises` Methods

| Method            | Description                                   |
| ----------------- | --------------------------------------------- |
| `fs.readFile()`   | Reads a file                                  |
| `fs.writeFile()`  | Writes to a file (creates or overwrites)      |
| `fs.appendFile()` | Appends data to a file                        |
| `fs.unlink()`     | Deletes a file                                |
| `fs.rename()`     | Renames or moves a file                       |
| `fs.mkdir()`      | Creates a directory                           |
| `fs.readdir()`    | Reads directory contents                      |
| `fs.stat()`       | Gets metadata for a file or directory         |
| `fs.rm()`         | Deletes files or folders (recursive too)      |
| `fs.copyFile()`   | Copies a file                                 |
| `fs.access()`     | Checks file or folder existence & permissions |

---

## 🔍 Example Usage with `promise chaining`

### 📖 Read File

```js
const fs = require("fs/promises");
const path = require("path");

const fileName = "fsPromises.txt";
const filePath = path.join(__dirname, fileName);

fs.readFile(filePath, "utf-8")
  .then((data) => console.log(data))
  .catch((err) => console.log(err));
```

### ✍️ Write File

```js
const fs = require("fs/promises");
const path = require("path");

const fileName = "fsPromises.txt";
const filePath = path.join(__dirname, fileName);

fs.writeFile(filePath, "Writing on this file using fs/promises")
  .then(() => console.log("Successfully wrote on ", fileName))
  .catch((err) => console.log(err));
```

### ➕ Append to File

```js
const fs = require("fs/promises");
const path = require("path");

const fileName = "fsPromises.txt";
const filePath = path.join(__dirname, fileName);

fs.appendFile(filePath, "\nAppend file is also working", "utf-8")
  .then(() => console.log("Successfully updated ", fileName))
  .catch((err) => console.log(err));
```

### 🗑️ Delete File

```js
const fs = require("fs/promises");
const path = require("path");

const fileName = "fsPromises.txt";
const filePath = path.join(__dirname, fileName);

fs.unlink(filePath)
  .then(() => console.log("Successfully Deleted ", fileName))
  .catch((err) => console.log(err));
```

### 📁 Create Directory

```js
// 📁 create-dir-promise.js
const fs = require('fs/promises');
const path = require('path');

const dirPath = path.join(__dirname, 'new-folder');

fs.mkdir(dirPath, { recursive: true }) // creates parent directories if they don't exists
  .then(() => {
    console.log('✅ Directory created successfully!');
  })
  .catch((err) => {
    console.error('❌ Failed to create directory:', err.message);
  });

```

### 📄 List Files in Directory

```js
// 📁 list-files.js
const fs = require('fs/promises');
const path = require('path');

const dirPath = path.join(__dirname, 'new-folder');

fs.readdir(dirPath)
  .then((files) => {
    console.log('📁 Files in directory:');
    files.forEach((file) => {
      console.log('•', file);
    });
  })
  .catch((err) => {
    console.error('❌ Failed to read directory:', err.message);
  });
```

---

## 🔧 Benefits of `fs/promises`

- Cleaner async code with `await`
- No need for callback hell
- Works well with `try-catch` for error handling
- Preferred for modern Node.js projects

---

## 🧵 Notes

- Always wrap `await` calls in `try-catch`
- Don’t forget to use `async` functions
- Use `path` module with `fs` for cross-platform compatibility

```js
const path = require('path');
const filePath = path.join(__dirname, 'example.txt');
await fs.readFile(filePath, 'utf8');
```

---

Let me know if you want a cheat sheet combining `fs`, `fs/promises`, and `fs/promises + path` usage!


## Related topics: 

- [[FS Module in Node.js - Sync]]
- [[FS Module in Node.js - Async]]

## References

