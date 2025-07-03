---
tags:
  - backend
  - express
status: 🟩
---

2025-07-02        11:10

### 🚦 Middlewares in Express.js

In **Express**, **middleware functions** are functions that have access to:

```js
(req, res, next)
```

They can:

- Modify `req` or `res`
    
- End the response (`res.send`, `res.json`, etc.)
    
- Or call `next()` to pass control to the next middleware
    

---

## 🧩 Types of Middleware

### 1. **Application-level middleware**

Applied to all routes or specific routes.

```js
app.use((req, res, next) => {
  console.log(`[LOG] ${req.method} ${req.url}`);
  next(); // Pass to the next middleware/route handler
});
```

---

### 2. **Route-level middleware**

Used only on specific routes.

```js
const checkAuth = (req, res, next) => {
  if (req.query.admin === 'true') next();
  else res.status(403).send('Not authorized');
};

app.get('/admin', checkAuth, (req, res) => {
  res.send('Welcome Admin');
});
```

---

### 3. **Built-in middleware**

Express provides a few built-in middleware:

```js
app.use(express.json());       // Parse JSON bodies
app.use(express.urlencoded({ extended: true })); // Parse form data
app.use(express.static('public')); // Serve static files from /public
```

---

### 4. **Third-party middleware**

Installed via `npm`.

```bash
npm install morgan cors
```

```js
const morgan = require('morgan');
const cors = require('cors');

app.use(morgan('dev')); // Log requests
app.use(cors());        // Enable Cross-Origin Resource Sharing
```

---

## 🔄 Order of Middleware Matters

Express runs middleware **in the order they're defined**:

```js
app.use(authMiddleware);
app.use(loggerMiddleware);
app.get('/', handler); // This will only run after the above middlewares
```

---

## 🔚 Middleware that ends the response

```js
app.use((req, res, next) => {
  res.status(404).send("Route not found");
});
```

---

## 💥 Error-handling middleware

Has **4 parameters** — `err, req, res, next`

```js
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(500).send('Something broke!');
});
```

---

## 🧪 Example – Custom Middleware

```js
const logger = (req, res, next) => {
  console.log(`[${new Date().toISOString()}] ${req.method} ${req.url}`);
  next();
};

app.use(logger); // Applies to all routes
```

---

## Related topics: 

- 

---
