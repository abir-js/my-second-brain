---
tags:
  - mysql
status: 🟩
---

2025-07-18        11:10

## **. Primary Key**

A **Primary Key (PK)** is a special column (or set of columns) used to **uniquely identify each row** in a table.

### Rules:

* Must be **unique** for each row.
* Cannot be `NULL`.
* Each table can have **only one Primary Key**, but it can be made up of multiple columns (What is a composite key).

---

### Example – `tech` Table

We create a `tech` table with `id` as the Primary Key.

```sql
CREATE DATABASE IF NOT EXISTS techdb;
USE techdb;

DROP TABLE IF EXISTS tech;

CREATE TABLE tech (
    id INT PRIMARY KEY AUTO_INCREMENT,        -- Primary Key with Auto Increment
    name VARCHAR(50) NOT NULL,
    category VARCHAR(50) NOT NULL,
    release_year INT CHECK (release_year >= 1990),
    website VARCHAR(100) UNIQUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

Insert sample data:

```sql
INSERT INTO tech (name, category, release_year, website)
VALUES
('React', 'Frontend', 2013, 'https://reactjs.org'),
('Node.js', 'Backend', 2009, 'https://nodejs.org'),
('MySQL', 'Database', 1995, 'https://mysql.com');
```

View data:

```sql
SELECT * FROM tech;
```

Here:

* `id` is the **Primary Key** (Auto Incremented).
* `website` is **Unique** (cannot repeat but is not a primary key).

---
