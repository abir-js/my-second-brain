---
tags:
  - mysql
status: 🟩
---

2026-01-21        02:27

---

## Database related commands

### Show all databases

```mysql
SHOW DATABASES;
```

### create database

```mysql
CREATE DATABASE myDb;
```

 
### use database

```mysql
USE myDb;
```

### show databases

```mysql
show databases;
```

### drop database

```mysql
DROP DATABASE myDb;
```

## Table related commands

### create table

```mysql
create table users (
	id INT PRIMARY KEY AUTO_INCREMENT,
	name VARCHAR(100),
	email VARCHAR(50) UNIQUE,
	age INT
	createdAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP
)
```

### Show all data from table

```mysql
SELECT * FROM users;
```

### update table structure

#### add columns

```mysql
ALTER TABLE users ADD gender VARCHAR(10);
```

#### modify columns

```mysql
ALTER TABLE users MODIFY age SMALLINT;
```

#### rename any column

```mysql
ALTER TABLE users CHANGE name fullName VARCHAR(100);
```

#### drop a column

```mysql
ALTER TABLE users DROP COLUMN age;
```

#### delete a table

```mysql
DROP TABLE users;
```

#### Describe a table structure

```mysql
DESC users;
```

---
