---
tags:
  - mysql
status: 🟩
---

2025-07-17        20:19

# Table queries in mysql

## 1. create a table in mysql

```mysql
CREATE TABLE games(
    name VARCHAR(50),
    ratings INT
);
```

## 2. Display list of all tables in database

```mysql
SHOW TABLES;
```

## 3. Display columns (fields) of a table

```mysql
SHOW COLUMNS FROM database_name;
```

## 4. Display/describe the structure of a table

```mysql
DESC table_name;
-- or
DESCRIBE table_name;
```

## 5. Set default value in table

```mysql
CREATE TABLE games(
    name VARCHAR(50) DEFAULT 'Anonymous',
    release_year INT DEFAULT 2025,
    ratings INT
);
```

## 6. Delete a table

```mysql
DROP TABLE table_name;
```

---
