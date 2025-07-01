---
tags:
  - nodejs
status: 🟩
---

2025-06-19        11:06

# 📂 Node.js `fs` Module

The `fs` module in Node.js allows you to **interact with the file system**—read, write, update, delete, and watch files or directories. It comes built-in with Node.js, so no installation is needed.

---

## ✅ Import the Module

```js
const fs = require('fs');
```

---

## 🔹 Common `fs` Methods

| Method                     | Description                                              |
|---------------------------|----------------------------------------------------------|
| `fs.readFile()`           | Reads a file asynchronously                              |
| `fs.readFileSync()`       | Reads a file synchronously                               |
| `fs.writeFile()`          | Writes to a file asynchronously (creates or overwrites) |
| `fs.writeFileSync()`      | Synchronous version of `writeFile`                       |
| `fs.appendFile()`         | Appends data to a file                                   |
| `fs.unlink()`             | Deletes a file                                           |
| `fs.rename()`             | Renames a file                                           |
| `fs.existsSync()`         | Checks if a file or directory exists                    |
| `fs.mkdir()`              | Creates a new directory                                  |
| `fs.readdir()`            | Reads contents of a directory                           |
| `fs.stat()`               | Returns metadata about a file or directory               |

---

## 🔍 Example Usage

### ✍️Write file (Sync)

**fs.writeFileSync():** writes data to a file. If the file does not exist, it will be created. If the file exists, it overwrites the content. 
Syntax => `fs.writeFileSync(filePath, data, options )`

 *  filePath => The file path to write to.
 *  data => The content
 *  options => Optional. Includes encoding('[[utf-8]]'), mode or flags.

```js
const fileName = "hello.txt"
const filePath = path.join(__dirname, fileName)

const fileData = fs.writeFileSync( filePath, "This is a test file", "utf-8" );

console.log(fileData); // undefined
```

### 📖Read file (Sync):

**fs.readFileSync():** Reads a file's content and returns it as a string or buffer.
 *  Syntax => `const data = fs.readFileSync(filePath, options);`
 *  `filepath` => path to the file to read.
 *  `options` => Optional. Use [[utf-8]] to get a string data.

```js
const fileName = "hello.txt"
const filePath = path.join(__dirname, fileName)

const readFile = fs.readFileSync(filePath, "utf-8")
console.log(readFile);
```

### ➕Append file (Sync):

**fs.appendFileSync():** Appends data to a file. If a file doesn't exists, it creates a file.
 *  Syntax => `const data = fs.appendFileSync(filePath, data, options);`
 *  `filepath` => path to the file to read.
 * `data` => Content to add in file
 *  `options` => Optional. Use [[utf-8]] to get a string data.

```js
const fileName = "hello.txt"
const filePath = path.join(__dirname, fileName)

const appendFile = fs.appendFileSync(
	filePath, 
	"\nThis is new line.", 
	"utf-8");
console.log(appendFile); // undefined
```

### 🗑️Delete file (Sync):

**fs.unlinkSync():** Deletes a file by its path.
 *  Syntax => `const data = fs.unlinkSync(filePath);`
 *  `filepath` => path to the file to read.

```js
const fileName = "hello.txt"
const filePath = path.join(__dirname, fileName)

const deleteFile = fs.unlinkSync(filePath);
console.log(appendFile); // undefined
```

### 📝Rename file (Sync):

**fs.renameSync():** Renames a file.
 *  Syntax => `const data = fs.renameSync(oldpath, newPath);`
 *  `filepath` => path to the file to read.
 * `newPath` => new path or name.
 
```js
const newUpdatedFileName = "hello2.txt"
const newUpdatedFilePath = path.join(__dirname, newUpdatedFileName)

const renameFile = fs.renameSync(filePath, newUpdatedFilePath);
console.log(renameFile); // undefined
```

---
## ⚠️ Notes

- Prefer **async methods** in production apps to avoid blocking the event loop.
- Wrap in `try-catch` when using **sync** methods to handle errors gracefully.

---

## 🔧 Use Cases

- Reading configuration files
- Logging to text files
- Creating simple file-based databases
- Managing uploads/downloads


## Related topics: 

- 

## References

