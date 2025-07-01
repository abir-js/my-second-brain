---
tags:
  - nodejs
  - cohort
status: 🟩
---

2025-06-24        11:37

# Node.js internals part 2?

![[nodejs-components.png|300]]

- Node js is a v8 engine written in c++

**Node.js is single threaded**
- means only one waiter, it can do one job at a time
- If there are multiple customers, the waiter will pass order to chief and take another order

In multithreaded
- There are multiple waiters.
- But each waiter have to serve a customer completely from taking order to serving

### LibUV

- libuv is a multi-platform C library that provides support for asynchronous I/O based on event loops. 

## Processes in Node.js


![[nodejs-architecture.png]]

```js
const fs = require("fs")

setTimeout(() => console.log("Set Timeout"), 0)

setImmediate(() => console.log("Set Immediate"))

fs.readFile("sample.txt", "utf-8", function(err, data) {
	setTimeout(() => console.log("Set Timeout inside FS"), 0)
	setImmediate(() => console.log("Set Immediate Inside FS"))
})

console.log("hello")

/*
hello
set timeout
setimmediate
set immediate inside fs
set timeout inside fs
*/
```

```
/*
step 1: 
- fs runs
- setTimeout kickoffs
- setImmediate kickoffs
- fs started excuting
- console.log gets printed

step 2:
- event loop gets started
- setTimeout gets printed
- suppose fs still working
- setImmediate gets printed
- no closed callback
- retry

step 3:
- no expired callback
- suppose fs completed // now on IO pooling phase
- setImmediate inside fs gets printed
- no closed callbacks
- retry

step 4:
- setTimeout insidefs gets printed
- no IO polling
- no setImmediate
- no closed callbacks
- ends
*/
```

## 🔬 Under the Hood:

When Node.js starts executing your script:

1. It runs all top-level code synchronously.
    
2. During this time, you call `setTimeout(..., 0)` and `setImmediate()`.
    
3. **Both are registered to their respective queues**:
    
    - `setTimeout(..., 0)` → timers phase queue
        
    - `setImmediate()` → check phase queue
        
4. Node then enters the event loop, and depending on **internal timing**, the **poll phase** (which sits between timers and check) may be:
    
    - Empty (no I/O)
        
    - Short-circuited
        
    - Completed so fast that the **check phase executes before the timers phase**
        

This means that:

- If poll completes quickly, Node goes to **check phase**, so `setImmediate()` fires first.
    
- If poll waits (e.g. to maintain a minimum delay for timers), `setTimeout(..., 0)` fires first.
---

## Thread Pool

- Suppose we are doing a very CPU intensive tasks like hashing password with multiple rounds.
- For that particular time, event loop will get blocked.
- For those tasks we use worker threads. 

**By default there are 4 workers threads**

`process.env.UV_THREADPOOL_SIZE = 6`


---
## Related topics: 

- 

---
