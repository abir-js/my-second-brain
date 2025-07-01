---
tags:
  - nodejs
  - cohort
status: 🟩
---

2025-06-23        00:41

# Node.js Internals

- Node.js is [[JavaScript runtime environment]].
- v8 engine + c++.
### Examples:

- Chrome - v8 (open-source)
- Deno - also made by Node.js delelopers.
- **Bun JS** - **Drop in replacement for Node.js**
- Spider Monkey - FireFox
- Apple WebKit - Safari
- original made by Node.js developers were FireFox.
- npm full form is not Node Package Manager.



```js
const fs = require("fs");
fs.writeFile("./test.txt", "Hello world", () => {});
```

## 1. Why it is not working in browser?

### Module function wrapper

![[module-function-wrapper.png]]

- Node.js executes our code inside a wrapper function.
- **_ _ filename**: gives file name
- _ _ dirname: gives current directory

## 2. We didn't installed fs, how it is using it

- `const fs = require("fs")` => here **fs is a id**.
- **require method takes an id** and searches for that in its internal module.
## 3. Require and Export in Node.js

```js
function __require(){
	// require("./math") -> khud ke internal module mei dhundo
	// require("fs") -> user ki dir mei code dhundo
	// agar nehi mila to node_modules nei dhundo
}
```

- require method **returns an Object**.
- Exports object mei jo bhi hai idhar le aau.
- Jo bhi bhejna hai exports function mei add kar do.

```js 
// math.js
// named export
exports.abir = "Hello I am Abir";

//index.js
const math = require("./math");
console.log(math.abir); // "Hello I am Abir";
```

> [!TIP] 
> We can't use require and export in react because it works on browser.

## 4. named vs default export

```js
// named export
exports.abir = "Hello I am Abir";

//index.js
const math = require("./math");
console.log(math.abir); // "Hello I am Abir";
```

```js
// deault export
const abir = "Hello I am Abir";
const add = (a, b) => a + b;

//==> for single variable
export default abir;

// for multiple variables
module.export = {abir, add}

//index.js
const math = require("./math");
console.log(math.abir); // "Hello I am Abir";
```

## 5. Sem Versioning

[[Semantic Versioning]]

![[semantic-versioning.png]]

## 6. http module

- `curl` - cURL is a CLI tool to make n/w requests.

```js
const express = require("express");
const http = require("http");

const handlerFunctionV2 = express();

handlerFunctionV2.get("/", (req, res) => res.end("Home page"));
handlerFunctionV2.get("/contact-us", (req, res) => res.end("Contact us page"));
handlerFunctionV2.get("/about-us", (req, res) => res.end("About us page"));

function handlerFunction(req, res) {
  //   console.log("Incoming request");
  //   console.log(req.method);
  //   console.log(req.url);
  //   res.end("Ye lo response");

  switch (req.method) {
    case "GET":
      {
        if (req.url === "/") return res.end("Home Page");
        if (req.url === "/contact") return res.end("Contact Page");
        if (req.url === "/about") return res.end("About Page");
      }
      break;
    case "POST":
      {
      }
      break;
    default:
      break;
  }
}

const server = http.createServer(handlerFunctionV2);

server.listen(8000, () => console.log("listening on port 8000"));
```

### koa, hono, fastify - http wrappers like express

---
## Related topics: 

- [[Node.js#6. Modules in Node.js | More about Modules]]
- 

---
