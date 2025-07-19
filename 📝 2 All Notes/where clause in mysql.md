---
tags: 
status:
---

2025-07-18        12:14

# Where clause

- WHERE keyword is used to **filter records** that meets a specific condition.
- It is typically used in SELECT, UPDATE, and DELETE statements to narrow down the results or specify which rows to update or delete.

### select all games where ratings is 5 👇

```mysql
SELECT title, genre FROM movies WHERE genre = "Action";
```

### select with aliases

```mysql
SELECT title as name FROM movies WHERE genre = "Action";
```

---
