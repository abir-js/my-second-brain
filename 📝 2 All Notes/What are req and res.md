---
tags:
  - nodejs
status: 🟩
---

2025-06-20        17:57

# 📘 Node.js – `req` and `res` Objects (with `http` module)

In Node.js, when you create a server using the built-in `http` module, two key objects are passed to the callback of `http.createServer()`:

```js
http.createServer((req, res) => {
  // req = request object
  // res = response object
});
```

---

## 🔹 1. `req` – Request Object

The `req` object is an instance of [`http.IncomingMessage`](https://nodejs.org/api/http.html#class-httpincomingmessage). It represents the **incoming HTTP request** from the client.

### ✅ Common Properties:

|Property|Description|
|---|---|
|`req.method`|HTTP method (`GET`, `POST`, `PUT`, etc.)|
|`req.url`|The requested URL (`/`, `/about`, etc.)|
|`req.headers`|Object containing request headers|
|`req.httpVersion`|HTTP version used (e.g., `'1.1'`)|

### ✅ Common Events (EventEmitter):

|Event|Description|
|---|---|
|`data`|Emitted when a data chunk is received (POST)|
|`end`|Emitted when all request data has been received|
|`error`|Emitted on error|

### 🧪 Example – Reading POST data:

```js
let body = '';

req.on('data', chunk => {
  body += chunk;
});

req.on('end', () => {
  console.log('Received body:', body);
});
```

---

## 🔹 2. `res` – Response Object

The `res` object is an instance of [`http.ServerResponse`](https://nodejs.org/api/http.html#class-httpserverresponse). It is used to **send back a response** to the client.

### ✅ Common Methods:

|Method|Description|
|---|---|
|`res.writeHead(status, headers)`|Sets HTTP status and headers|
|`res.setHeader(name, value)`|Sets a single header|
|`res.write(data)`|Writes data to response body|
|`res.end([data])`|Ends the response|

### ✅ Common Events (EventEmitter):

|Event|Description|
|---|---|
|`finish`|Emitted when the response is fully sent|
|`close`|Emitted when the connection is closed|
|`error`|Emitted if a stream error occurs|

### 🧪 Example – Sending a response:

```js
res.writeHead(200, { 'Content-Type': 'text/plain' });
res.write('Hello ');
res.end('World!');
```

---

## 🔄 Combined Example with Routing

```js
const http = require('http');

const server = http.createServer((req, res) => {
  if (req.url === '/' && req.method === 'GET') {
    res.writeHead(200, { 'Content-Type': 'text/html' });
    res.end('<h1>Welcome to Home Page</h1>');
  } else if (req.url === '/about') {
    res.writeHead(200, { 'Content-Type': 'text/plain' });
    res.end('About Page');
  } else {
    res.writeHead(404, { 'Content-Type': 'text/plain' });
    res.end('404 Not Found');
  }
});

server.listen(3000, () => {
  console.log('Server running on http://localhost:3000');
});
```

---

## 🔁 Are `req` and `res` EventEmitters?

✅ **Yes.** Both `req` and `res` inherit from `EventEmitter`.

- `req` (IncomingMessage) → `ReadableStream` → `EventEmitter`
    
- `res` (ServerResponse) → `WritableStream` → `EventEmitter`
    

This allows you to use `.on()`, `.emit()`, etc.

---

## 📝 Summary Table

|Feature|`req`|`res`|
|---|---|---|
|Class|`http.IncomingMessage`|`http.ServerResponse`|
|Type|Readable Stream (`EventEmitter`)|Writable Stream (`EventEmitter`)|
|Role|Represents client's request|Used to send response to client|
|Used for|Reading method, URL, headers, body|Sending status, headers, and body|


## Related topics: 

-  [[HTTP Module in Node.js]]
- [[What are Streams]]

## References

