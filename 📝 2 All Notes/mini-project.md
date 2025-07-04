---
tags:
  - backend
  - express
status: 🟩
---

2025-07-03        15:33

# Flow of auth

1. create basic express app with dotenv
2. add global middleware for logger
3. create public private routes

### logger ✅

1. take filename and dirname using os, path, url.
2. if the log folder does not exists, create it.
3. create log.middlewares.js,
	1. take filename and dirname using os, path, url.
	2. create log middleware
		1. log data, log file
4. use it as global middleware in index.js ✅

### public routes ✅

1. create a "/" route
2. create a "/generate-token" route
	1. generate token using generate token function from token.utils.js
	2. send message, token

### private routes ✅

1. create "/dashboard route"

### generate token ✅

1. in utils folder, create token.utils.js
2. create a generate token function that will return token using crypto
3. create validate token function which will validate using token length
### auth

1. create auth.middleware.js 
2. take token from header
3. validate token using validate token method from token.utils.js
	1. if true
		1. send random id with username
	2. else
		1. send error

---
## Related topics: 

- 

---
