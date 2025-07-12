---
tags:
  - backend
  - express
status: 🟩
---

2025-07-05        01:03



```js
import express from "express"
const app = express()

// route parameters
app.get("/product", (req, res) => {
	const {course} = req.query;
})

app.listen(8080, () => console.log("app is listening on port 8080"))
```

---
## Related topics: 

- 

---
