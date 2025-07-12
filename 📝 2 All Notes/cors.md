---
tags:
  - backend
  - cohort
status: 🟩
---

2025-06-30        12:27

# What are cors?

CORS, or Cross-Origin Resource Sharing, is ==a browser security feature that controls how a web page can make requests to a different domain than the one that served the page==. It's a mechanism that allows servers to specify which origins are permitted to access their resources, essentially relaxing the "same-origin policy" that would otherwise block such requests. 

```js
import express from "express";
import dotenv from "dotenv";
import cors from "cors";

dotenv.config();

const app = express();
const PORT = process.env.PORT || 4000;

//?cors
app.use(
  cors({
    origin: `process.env.BASE_URL`,
    credentials: true,
    methods: ["GET", "POST", "DELETE", "OPTIONS"],
    allowedHeaders: ["Content-Type", "Authorization"],
  })
);

app.get("/", (req, res) => {
  res.send("Hello, Express!");
});

app.listen(PORT, () => {
  console.log(`Server is running on http://localhost:${PORT}`);
});
```

Here's a more detailed explanation:

## What is the Same-Origin Policy?

The same-origin policy is a fundamental security measure in browsers that restricts web pages from making requests to a different domain than the one that served the page. This is to prevent malicious websites from accessing sensitive data on other domains without authorization. 

## Why do we need CORS?

While the same-origin policy is important for security, it can be too restrictive for legitimate use cases. For example, a web application might need to fetch data from a third-party API, or a website might need to load resources (like fonts or images) from a different domain. CORS provides a controlled way to bypass the same-origin policy and allow these types of cross-origin requests. 

## How does CORS work?

- **1.** **The browser sends a request:**
    
    When a web page makes a cross-origin request, the browser adds an "Origin" header to the request, indicating the origin of the page making the request.
    

- **2.** **The server responds:**
    
    The server receiving the request can include an "Access-Control-Allow-Origin" header in its response. This header specifies which origins are allowed to access the resource.
    

- **3.** **The browser checks the response:**
    
    If the "Access-Control-Allow-Origin" header matches the origin of the request, the browser allows the response to be used by the web page. If it doesn't match, the request is blocked. 
    

## Example:

Imagine a website hosted on `https://www.example.com` tries to fetch data from `https://api.example.net`. Without CORS, this request would be blocked by the browser. However, if `https://api.example.net` includes an "Access-Control-Allow-Origin: https://www.example.com" header in its response, the browser will allow the request to succeed. 

Key points about CORS:

- **CORS is not a security measure against all cross-origin attacks:**
    
    While CORS helps with some security concerns, it's not a complete protection against all cross-origin attacks, such as cross-site request forgery (CSRF). 
    

- **CORS can be configured with different options:**
    
    Servers can configure CORS to allow access from specific origins, or from any origin using the wildcard character (`*`). 
    

- **CORS can involve preflight requests:**
    
    For certain types of requests (like those using methods other than GET, HEAD, or POST, or those with custom headers), the browser may first send a "preflight" request (an OPTIONS request) to the server to check if the actual request is allowed.

![[cors-backend.png]]

---
## Related topics: 

- 

---
