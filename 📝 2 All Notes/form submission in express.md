---
tags:
  - backend
  - express
status: 🟩
---

2025-07-09        20:46

# How to handle form submission in express?

- By default, form uses `GET` request, and you can handle with `app.get()` to access form data via `req.query` 
	
- Since URLs have a length limit, you can use the `POST` method for form submissions, which sends the data in the request body
	
- To access data from POST request, we use [[express.urlencoded()]] middleware to parse the request body.

	- The urlencoded option `{extented: true}` uses **qs** library to parse the query string, allowing for more complex structures like nested objects, which the default parser can't handle.

---
## Related topics: 

- 

---
