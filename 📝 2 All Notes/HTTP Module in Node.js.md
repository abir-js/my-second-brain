---
tags:
  - nodejs
status: 🟩
---

2025-06-20        17:47

# HTTP Module in Node.js

The `http` module in Node.js is a built-in module that allows you to create an HTTP server and handle HTTP requests and responses. It’s part of Node’s core modules, so you **don’t need to install it**—just `require` it in your code.

---

## 🔧 Basic Usage

### ✅ Create a simple HTTP server:

```js
const http = require('http');

const server = http.createServer((req, res) => {
  // Set response header
  res.writeHead(200, { 'Content-Type': 'text/plain' });

  // Send response
  res.end('Hello, World!');
});

// Start server on port 3000
server.listen(3000, () => {
  console.log('Server running at http://localhost:3000/');
});
```

---

## 📦 Common Properties & Methods

### `http.createServer([options], requestListener)`

- Creates a new HTTP server instance.
- `requestListener` is a function with parameters `(req, res)`.

### `req` (IncomingMessage)

- `.url` – The request URL (`/about`)
    
- `.method` – HTTP method (`GET`, `POST`)
    
- `.headers` – Request headers object

### `res` (ServerResponse)

- `.writeHead(statusCode, headers)` – Set status code and headers
    
- `.write(data)` – Send data chunk to response
    
- `.end([data])` – End response

---

## 🌐 Example with Routing

```js
const http = require('http');

const server = http.createServer((req, res) => {
  res.setHeader('Content-Type', 'text/html');

  if (req.url === '/') {
    res.statusCode = 200;
    res.end('<h1>Home Page</h1>');
  } else if (req.url === '/about') {
    res.statusCode = 200;
    res.end('<h1>About Page</h1>');
  } else {
    res.statusCode = 404;
    res.end('<h1>404 Not Found</h1>');
  }
});

server.listen(3000, () => {
  console.log('Server running on http://localhost:3000');
});
```

---

## 📥 Handling POST Data

```js
const http = require('http');

const server = http.createServer((req, res) => {
  if (req.method === 'POST') {
    let body = '';
    req.on('data', chunk => {
      body += chunk.toString(); // Convert buffer to string
    });
    req.on('end', () => {
      console.log('Received data:', body);
      res.end('Data received');
    });
  } else {
    res.end('Send a POST request');
  }
});

server.listen(3000);
```

---

## 💡 Summary

|Feature|Description|
|---|---|
|`createServer()`|Creates a new HTTP server|
|`req`|Incoming request object|
|`res`|Response object|
|`listen(port)`|Starts the server|

---

Let me know if you want to serve static files, parse JSON, or build a REST API using `http`.

## Related topics: 

- 

## References

