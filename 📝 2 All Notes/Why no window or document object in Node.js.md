---
tags:
  - nodejs
status: 🟩
---

2025-06-18        17:12

# Why no window or document object in Node.js?

- In Node.js, there is no window or document. Because Node.js runs outside the browser - it doesn't  deal with DOM and browser-specific APIs.

- Instead, Node.js has a [[Global Object in Node.js | global]] object. It's equivalent of window in the browser but designed for a server side environment.

```JavaScript
global.console.log("Hello World");
```

## Related topics: 

- what is [[Global Object in Node.js]] in Node.js

## References

