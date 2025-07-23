---
tags:
  - mysql
status: 🟩
---

2025-07-22        12:56

---
## **Transactions & Commit**

A **transaction** allows you to group multiple SQL statements as **one unit of work**.
You can either:

* **Commit**: Save all changes permanently.
* **Rollback**: Undo all changes.

By default, MySQL uses **autocommit (every statement is committed automatically)**.

---

### Example Transaction:

```sql
-- Turn off autocommit
SET autocommit = 0;

-- Insert multiple records
INSERT INTO tech (name, category, release_year, website)
VALUES ('Vue.js', 'Frontend', 2014, 'https://vuejs.org');

INSERT INTO tech (name, category, release_year, website)
VALUES ('Angular', 'Frontend', 2010, 'https://angular.io');

-- If everything is correct, save changes
COMMIT;

-- If something went wrong, undo changes instead
-- ROLLBACK;

-- Re-enable autocommit
SET autocommit = 1;
```


---
