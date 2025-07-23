---
tags:
  - mysql
status:
---

2025-07-22        11:13

---
## **1. What are Constraints in MySQL?**

**Constraints** are rules applied to table columns to ensure **data integrity** (data remains valid and consistent).

### Types of Constraints:

1. **NOT NULL** – The column must always have a value.
2. **UNIQUE** – Each value in the column must be unique (no duplicates).
3. **PRIMARY KEY** – Uniquely identifies every row (cannot be `NULL` and is automatically `UNIQUE`).
4. **FOREIGN KEY** – Links a column to a Primary Key in another table (creates relationships).
5. **CHECK** – Ensures values meet a condition (e.g., `age > 0`).
6. **DEFAULT** – Assigns a default value if none is given.


---
