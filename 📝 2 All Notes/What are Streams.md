---
tags:
  - nodejs
status: 🟩
---

2025-06-20        17:59

# 📘 What Are Streams in Node.js?

A **stream** is a **sequence of data** that is read or written **over time**, instead of loading the entire data into memory all at once.

### 🚀 Why Use Streams?

Streams are useful when working with:

- **Large files** (video/audio logs, etc.)
    
- **Network communication** (HTTP requests/responses)
    
- **Real-time data processing** (e.g. reading logs)
    

---

## 🔁 Analogy

> 📦 Think of a stream like a water pipe. You don’t wait for the entire tank to be full — you get water **as it flows**.

---

## ✅ Types of Streams in Node.js

|Stream Type|Direction|Description|Example|
|---|---|---|---|
|**Readable**|**Read from**|Data can be read from this stream|`fs.createReadStream()`|
|**Writable**|**Write to**|Data can be written to this stream|`fs.createWriteStream()`|
|**Duplex**|Read + Write|Both readable and writable|`net.Socket`|
|**Transform**|Read + Write|Like duplex, but can modify (transform) data|`zlib.createGzip()`|

---

## 🧪 Basic Example: Read a File Using Stream

```js
const fs = require('fs');

const readableStream = fs.createReadStream('largefile.txt', {
  encoding: 'utf8',
  highWaterMark: 1024, // 1KB chunks
});

readableStream.on('data', (chunk) => {
  console.log('Received chunk:', chunk);
});

readableStream.on('end', () => {
  console.log('Finished reading');
});
```

---

## ✏️ Writable Stream Example

```js
const fs = require('fs');

const writableStream = fs.createWriteStream('output.txt');

writableStream.write('Hello, ');
writableStream.write('world!');
writableStream.end(); // closes the stream
```

---

## 🔗 Piping Streams (Read → Write)

```js
const fs = require('fs');

const reader = fs.createReadStream('input.txt');
const writer = fs.createWriteStream('output.txt');

reader.pipe(writer); // Reads and writes chunk-by-chunk
```

---

## 🔥 Streams Are Event Emitters

All stream objects are instances of **EventEmitter** and emit events like:

|Event|Description|
|---|---|
|`data`|Emitted when a chunk of data is available|
|`end`|Emitted when all data is consumed|
|`error`|Emitted on error|
|`finish`|(Writable) Emitted when all data is written|

---

## 📌 Real-World Use Cases

- Serving video/audio files chunk-by-chunk
    
- Uploading/downloading files
    
- Processing live logs
    
- Reading large JSON/CSV line by line
    

---

## 📜 Summary

|Feature|Explanation|
|---|---|
|Stream|Way to handle data piece-by-piece|
|Memory-efficient|Doesn't load entire file into RAM|
|Types|Readable, Writable, Duplex, Transform|
|Based on|`EventEmitter` (supports `.on()` and `.pipe()`)|

---

Let me know if you want a visual diagram of how data flows in streams or want to explore custom streams!

## Related topics: 

- [[HTTP Module in Node.js]]
- [[What are req and res]]

## References

