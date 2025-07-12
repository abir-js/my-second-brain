---
tags:
  - backend
  - project
status:
---

2025-07-12        12:31

# project

### structure

```js
Project/ 
├── node_modules/ 
├── controllers/ 
│ ├── auth.controller.js 
│ └── task.controller.js 
├── data/ 
├── middlewares/ 
│ └── auth.middleware.js 
├── routes/ 
│ ├── auth.route.js 
│ └── task.route.js 
├── utils/ 
├── index.js 
├── package.json 
└── pnpm-lock.yml
```


---

## 🔐 Session Authentication (Username Only) – Steps

### 1. **Enable sessions in your main server file**


- Use `express-session` middleware.
    
- Set it up before routes, with a secret and basic options.
    

---

### 2. **Create the `/login` route**

- In `auth.route.js`, define a `POST /login` route.
    
- Call the controller function: `loginUser`.
    

---

### 3. **Handle login logic in `auth.controller.js`**

- Get the `username` from `req.body`.
    
- If it's provided, store it in `req.session.user = { username }`.
    
- Send a success response.
    

---

### 4. **Create an `auth.middleware.js` file**

- Write a middleware function: `isAuthenticated`.
    
- Check if `req.session.user` exists.
    
- If yes → `next()`, else → return `401 Unauthorized`.
    

---

### 5. **Apply `isAuthenticated` middleware to protected routes**

- In `task.route.js`, apply it to routes like:
    
    - `GET /tasks`
        
    - `POST /tasks`
        
    - etc.
        

---

### 6. **Create the `/logout` route**

- In `auth.route.js`, define a `POST /logout` route.
    
- In controller, call `req.session.destroy()` to end the session.
    
- Send a logout confirmation.
    

---

### 7. **(Optional) Add a route like `/me`**

- Returns the current logged-in user info from session.
    
- Useful to check if session is active.
    

---



---
## Related topics: 

- 

---
