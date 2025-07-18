---
tags:
  - backend
status: 🟩
---

2025-07-17        11:27

## 🆚 **2. SQL vs NoSQL Databases**

| Feature            | SQL (Relational)                       | NoSQL (Non-Relational)                     |
| ------------------ | -------------------------------------- | ------------------------------------------ |
| **Data Format**    | Tables with rows and columns           | Document, Key-Value, Graph, Column         |
| **Schema**         | Fixed schema (structured)              | Dynamic schema (flexible)                  |
| **Scalability**    | Vertical (add resources to one server) | Horizontal (add more servers)              |
| **Examples**       | MySQL, PostgreSQL, Oracle              | MongoDB, Firebase, Cassandra               |
| **Query Language** | SQL                                    | No fixed language, uses JSON-style queries |
| **Best Use Case**  | Banking, ERP, structured data          | Real-time apps, IoT, big data              |

### 🔹 Example:

- **SQL**:

```
SELECT * FROM users WHERE age > 30;
```

- **NoSQL (MongoDB)**:

```
db.users.find({ age: { $gt: 30 } });
```

---

---
