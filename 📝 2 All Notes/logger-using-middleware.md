---
tags:
  - backend
  - express
status: 🟩
---

2025-07-02        17:00

```js
import express from "express";
import fs from "fs";
import dotenv from "dotenv";

dotenv.config();

const app = express();
const PORT = process.env.PORT || 4000;

//? global middlewares
function logger(req, res, next) {
  const data = `{${new Date().toISOString()}} - ${req.method} - ${req.url} \n`;
  fs.appendFile("./logger.txt", data, "utf-8", (err) => {
    if (err) res.send(err.message);
    next();
  });
}

app.use(logger);

app.get("/", (req, res) => {
  res.send("Hello from Express ");
});

app.listen(PORT, () => {
  console.log(`Server running on http://localhost:${PORT}`);
});
```

---
## Related topics: 

- 

---
