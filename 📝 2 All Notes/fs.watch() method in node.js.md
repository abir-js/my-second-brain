---
tags:
  - nodejs
status: 🟩
---

2025-06-20        10:29

### 📡 `fs.watch()` in Node.js

`fs.watch()` allows you to **watch for changes** (like modify, rename, delete) in a file or directory.

It’s great for:

- Live-reloading apps
    
- Monitoring logs/configs
    
- Auto-building code
    

---

## 🔧 Syntax:

```js
fs.watch(filename[, options], listener)
```

- `filename`: The file or directory to watch.
    
- `options`: Optional object (like `{ recursive: true }` for directories).
    
- `listener(eventType, filename)`: Callback triggered on change.
    

---

## ✅ Basic Example: Watch a File

```js
const fs = require('fs');

fs.watch('hello.txt', (eventType, filename) => {
  console.log(`Event: ${eventType}`);
  console.log(`File affected: ${filename}`);
});
```

Try editing or saving `hello.txt` — it will log:

```
Event: change
File affected: hello.txt
```

---

## ✅ Watch a Directory

```js
fs.watch('./my-folder', (eventType, filename) => {
  console.log(`${filename} was ${eventType}`);
});
```

> If you add, delete, or rename files inside `my-folder`, it will trigger.

---

## ⚙️ Optional Options

```js
fs.watch('file.txt', {
  persistent: true,      // Keep process running
  encoding: 'utf8',
  recursive: false       // If true, watches subfolders (on macOS/Windows)
}, (eventType, filename) => {
  console.log(`${eventType} on ${filename}`);
});
```

---

## ⚠️ Caveats

- Not 100% reliable on **Linux** for directories — prefer `fs.watchFile()` or packages like `chokidar` for robust needs.
    
- May emit `rename` on edits (depends on OS).
    
- `filename` may be `undefined` sometimes.
    

---

## 🧠 Best Practice – Use `chokidar` for production

```bash
npm install chokidar
```

```js
const chokidar = require('chokidar');

chokidar.watch('somefile.txt').on('change', (path) => {
  console.log(`${path} has changed`);
});
```

---
## Related topics: 

- 

## References

