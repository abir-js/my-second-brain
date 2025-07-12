---
tags:
  - backend
  - cohort
  - mongoose
status: 🟩
---

2025-06-30        20:55

# How to connect to MongoDB

### 1. Install mongoose

```js
npm i mongoose
```

### 2. Create separate file for db connection

```
example_app / 
	└── utils/ 
		└── db.js
```

```js
// utils/db.js
import mongoose from "mongoose";
import dotenv from "dotenv";

dotenv.config();

// Export a function that connects to db
const db = () => {
  mongoose
    .connect(process.env.MONGO_URL)
    .then(() => {
      console.log("Connected to Mongodb");
    })
    .catch((err) => {
      console.log("Failed to connect to MongoDB", err);
    });
};
  
export default db;
```

### 3. Use it in index.js

```js
import db from "./utils/db.js";
await db();
```

---
## Related topics: 

- 

---
