---
tags:
  - nodejs
status: 🟩
---

2025-06-20        10:30

# 🔊 What are **Event Emitters** in Node.js?

In Node.js, an **EventEmitter** is a core class provided by the `events` module that allows you to **handle asynchronous events** by emitting and listening for them — just like how a button click emits an event in the browser.

---

### 🧠 Concept:

Think of it as a **radio station**:

- The station **emits** signals (events).
    
- Your radio **listens** for those signals and reacts accordingly.
    

---

### 📦 Provided by:

```js
const EventEmitter = require('events');
```

---

### 🛠️ Common Methods:

|Method|Description|
|---|---|
|`.on(eventName, listener)`|Register a listener for the event|
|`.emit(eventName, [args])`|Trigger the event|
|`.once(eventName, listener)`|Listen **only once**|
|`.removeListener()` / `.off()`|Remove a specific listener|

---

### ✅ Simple Example:

```js
const EventEmitter = require('events');
const emitter = new EventEmitter();

emitter.on('greet', (name) => {
  console.log(`Hello, ${name}`);
});

emitter.emit('greet', 'Abir');
```

**Output:**

```
Hello, Abir
```

---

### 🔍 Real Use Cases:

- Listening for **HTTP requests** in servers.
    
- Handling **file read/write events**.
    
- Building **custom event-driven systems**.
    
- Used under the hood in many Node.js core modules (like `fs`, `http`, `net`, etc.).

---

### 🧩 Analogy:

| Web Browser          | Node.js                   |
| -------------------- | ------------------------- |
| `onclick` event      | `emitter.on("event", cb)` |
| `dispatchEvent(...)` | `emitter.emit("event")`   |

---
## Related topics: 

-  [[Event Emitter Tasks]]

## References

