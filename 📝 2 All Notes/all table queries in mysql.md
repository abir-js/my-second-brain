---
tags:
  - mysql
status: 🟨
---

2025-07-19        13:08

# What is Title?



---
## 1. create a table in mysql

```mysql
CREATE TABLE games(
    name VARCHAR(50),
    ratings INT
);
```

### A. Set default value in table

```mysql
CREATE TABLE games(
    name VARCHAR(50) DEFAULT 'Anonymous',
    release_year INT DEFAULT 2025,
    ratings INT
);
```

---
## 2. Display data from table

### A. Display list of all tables in database

```mysql
SHOW TABLES;
```

### B. Display columns (fields) of a table

```mysql
SHOW COLUMNS FROM table_name;
```

### C. Display/describe the structure of a table

```mysql
DESC table_name;
-- or
DESCRIBE table_name;
```

---

## 3. Delete a table

### 1. Delete a table

```mysql
DROP TABLE table_name;
```

## 4. Insert data in table

```mysql
INSERT INTO games (name, relese_year, ratings)
VALUES ('gta-5', 2011, 10),
    ('PUBG', 2017, 8);
```
## 5. Selecting data from table

### A. select everything from table

```mysql
SELECT * FROM games;
```
### B. select particular column from table

```mysql
SELECT name, ratings, relese_year FROM games;
```

