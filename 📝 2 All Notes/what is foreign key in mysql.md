---
tags:
  - mysql
status: 🟩
---

2025-07-22        12:35

---
# **Foreign Key**

A **Foreign Key (FK)** is a column in one table that **references a Primary Key in another table**.
It enforces **referential integrity** (a row can only refer to an existing parent row).

### Why use Foreign Keys?

* To link tables (relationships).
* To prevent invalid references.
* To define what happens when parent rows are **deleted or updated**.

---

### Example – `frameworks` Table

Each framework belongs to a technology in the `tech` table.

```mysql
DROP TABLE IF EXISTS frameworks;

CREATE TABLE frameworks (
    id INT PRIMARY KEY AUTO_INCREMENT,
    tech_id INT,  -- Foreign Key referencing tech.id
    framework_name VARCHAR(50) NOT NULL,
    version VARCHAR(10) DEFAULT '1.0',
    CONSTRAINT fk_tech FOREIGN KEY (tech_id)
        REFERENCES tech(id)
        ON DELETE CASCADE
        ON UPDATE CASCADE
);
```

What this means:

* `tech_id` must match an existing `id` from `tech`.
* If a `tech` row is **deleted**, all its frameworks will also be deleted (`ON DELETE CASCADE`).
* If a `tech` row’s `id` is updated, the `tech_id` in `frameworks` is updated automatically (`ON UPDATE CASCADE`).

Insert sample frameworks:

```sql
INSERT INTO frameworks (tech_id, framework_name, version)
VALUES
(1, 'Next.js', '13'),   -- Related to React
(2, 'Express.js', '4'), -- Related to Node.js
(3, 'InnoDB', '1.0');   -- Related to MySQL
```

View data:

```sql
SELECT * FROM frameworks;
```

Test cascading delete:

```sql
DELETE FROM tech WHERE id = 2;  -- Deletes Node.js AND its framework (Express.js)
SELECT * FROM frameworks;       -- Express.js is now gone
```


---
