---
tags:
  - nodejs
status: 🟩
---

2025-06-19        10:34

# 🖥️ Node.js `os` Module

The `os` module in Node.js provides built-in methods to get information about the operating system, such as CPU, memory, platform, and network interfaces.

---

## ✅ Import the Module

```js
const os = require('os');
```

---

## 🔹 Common `os` Module Methods

| Method                    | Description                                        |
|--------------------------|----------------------------------------------------|
| `os.arch()`              | Returns the CPU architecture (`x64`, `arm`, etc.)  |
| `os.platform()`          | OS platform (`win32`, `linux`, `darwin`, etc.)     |
| `os.type()`              | OS name (`Windows_NT`, `Linux`, etc.)              |
| `os.hostname()`          | Hostname of the machine                            |
| `os.release()`           | OS version                                         |
| `os.uptime()`            | System uptime in seconds                           |
| `os.totalmem()`          | Total system memory in bytes                       |
| `os.freemem()`           | Free system memory in bytes                        |
| `os.userInfo()`          | Returns the current user information               |
| `os.cpus()`              | Information about each logical CPU core            |
| `os.networkInterfaces()` | Info about network interfaces                      |
| `os.homedir()`           | Returns the user's home directory                  |
| `os.tmpdir()`            | Temporary files directory                          |
| `os.endianness()`        | CPU endianness (`BE` or `LE`)                      |

---

## 🔍 Example Usage

```js
const os = require('os');

console.log("OS Platform:", os.platform());
console.log("CPU Architecture:", os.arch());
console.log("Total Memory:", os.totalmem() / (1024 ** 3), "GB");
console.log("Free Memory:", os.freemem() / (1024 ** 3), "GB");
console.log("Uptime (minutes):", os.uptime() / 60);
console.log("Home Directory:", os.homedir());
console.log("User Info:", os.userInfo());
```

---

## 🔧 Use Cases

- System health monitoring
- CLI tools that show system info
- Diagnostics and performance logging


## Related topics: 

- [[Path Module in Node.js]]

## References

