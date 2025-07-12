---
tags:
  - backend
  - express
status: 🟩
---

2025-07-05        00:52

```js
import express from "express"
const app = express()

// route parameters
app.get("/profile/:username/article/:slug", (req, res) => {
	res.send(<h1>Article ${req.params.username} by ${req.params.slug.replace(/-/g, " ")}</h1>)
})

app.listen(8080, () => console.log("app is listening on port 8080"))
```

```js
localhost:8080/profile/abir/article/how-to-learn-expressjs
```

---
## Related topics: 

- 

---
