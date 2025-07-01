---
tags:
  - nodejs
status: 🟨
---

2025-06-25        11:00

# How Node.js works?

## Synchronous vs Asynchronous

| Synchronous Code                           | Asynchronous Code                        |
| ------------------------------------------ | ---------------------------------------- |
| Tasks are executed sequentially.           | Tasks don't block execution.             |
| Each task blocks the next until completed. | Uses callbacks, promises, or async/await |
### Synchronous Code

```js
const data = fs.readfileSync("data.txt", "utf-8");
console.log(data);
```

### Asynchronous Code

```js
fs.readfile("data.txt", "utf-8", (data, err) => {
	if(err) console.log(err);
	else console.log(data);
})
```

---

## v8 engine

- Google's high-performance JavaScript engine that compiles JavaScript code into machine code.

## Libuv

- A C library that provides Node.js with cross-platform support for asynchronous I/O operations, file system, networking, and more.
- Includes the [[event loop in Node.js]] and [[thread pool]], enabling non-blocking tasks like file reading, networking and timers.

![[nodejs-architecture.png]]

![[how-nodejs-program-starts.png]]

![[nodejs-graph.png]]

---
## Related topics: 

- 

---
