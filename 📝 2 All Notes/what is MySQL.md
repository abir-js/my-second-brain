---
tags:
  - mysql
status: 🟩
---

2025-07-09        21:28

# What is MySQL?

- MySQL is a widely used open-source relational database management system (RDBMS)
	
- It stores data in tables, with rows representing individual records and columns representing data attributes.
	
- MySQL usus Structured Query Language (SQL) for managing and manipulating data.

- It is known for its reliability, performance, and ease of use, making it suitable for both small and large applications. 
	
- MySQL is cross platform supported.

 ---

## 🐬 **3. Introduction to MySQL**
MySQL is a **popular open-source relational database** based on SQL. It is widely used for:

- Web applications (e.g., WordPress)
- Data warehousing
- E-commerce and analytics

### 🔹 MySQL Key Features:

- Supports transactions
- Foreign key constraints
- High performance and reliability
- Open-source with enterprise support

---

## 🗃️ **4. Database-Related Queries**

### [🔹 Create a Database](https://surajkumarjha.me/blog/my-sql-day-1#-create-a-database)

```mysql
CREATE DATABASE mydb;
```

### 🔹 Use a Database

```mysql
USE mydb;
```

### 🔹 Show Databases

```mysql
SHOW DATABASES;
```

### [🔹 Drop a Database](https://surajkumarjha.me/blog/my-sql-day-1#-drop-a-database)

```mysql
DROP DATABASE mydb;
```

---

## [📋 **5. Table-Related Queries**](https://surajkumarjha.me/blog/my-sql-day-1#-5-table-related-queries)

### [🔹 Create Table](https://surajkumarjha.me/blog/my-sql-day-1#-create-table)

```mysql
CREATE TABLE users (  id INT PRIMARY KEY AUTO_INCREMENT,  name VARCHAR(100),  email VARCHAR(100) UNIQUE,  age INT,  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP);
```

### [🔹 Alter Table](https://surajkumarjha.me/blog/my-sql-day-1#-alter-table)

#### [Add a Column:](https://surajkumarjha.me/blog/my-sql-day-1#add-a-column)

```mysql
ALTER TABLE users ADD gender VARCHAR(10);
```

#### [Modify Column:](https://surajkumarjha.me/blog/my-sql-day-1#modify-column)

```mysql
ALTER TABLE users MODIFY age SMALLINT;
```

#### [Rename Column:](https://surajkumarjha.me/blog/my-sql-day-1#rename-column)

```mysql
ALTER TABLE users CHANGE name full_name VARCHAR(100);
```

#### [Drop Column:](https://surajkumarjha.me/blog/my-sql-day-1#drop-column)

```mysql
ALTER TABLE users DROP COLUMN gender;
```

#### [Rename Table:](https://surajkumarjha.me/blog/my-sql-day-1#rename-table)

```mysql
RENAME TABLE users TO customers;
```

### [🔹 Drop Table](https://surajkumarjha.me/blog/my-sql-day-1#-drop-table)

```mysql
DROP TABLE users;
```

### [🔹 Describe Table Structure](https://surajkumarjha.me/blog/my-sql-day-1#-describe-table-structure)

```mysql
DESCRIBE users;
```

---

## [🔍 **6. SELECT (Basic Query)**](https://surajkumarjha.me/blog/my-sql-day-1#-6-select-basic-query)

### [🔹 Select All Rows](https://surajkumarjha.me/blog/my-sql-day-1#-select-all-rows)

```mysql
SELECT * FROM users;
```

### [🔹 Select Specific Columns](https://surajkumarjha.me/blog/my-sql-day-1#-select-specific-columns)

```mysql
SELECT name, age FROM users;
```

### [🔹 Where Condition](https://surajkumarjha.me/blog/my-sql-day-1#-where-condition)

```mysql
SELECT * FROM users WHERE age > 25;
```

### [🔹 Order By](https://surajkumarjha.me/blog/my-sql-day-1#-order-by)

```mysql
SELECT * FROM users ORDER BY age DESC;
```

### [🔹 Limit Results](https://surajkumarjha.me/blog/my-sql-day-1#-limit-results)

```mysql
SELECT * FROM users LIMIT 5;
```

### [🔹 Aliases](https://surajkumarjha.me/blog/my-sql-day-1#-aliases)

```mysql
SELECT name AS full_name FROM users;
```

---

## [✍️ **7. INSERT Query (Basic)**](https://surajkumarjha.me/blog/my-sql-day-1#%EF%B8%8F-7-insert-query-basic)

### [🔹 Insert One Record](https://surajkumarjha.me/blog/my-sql-day-1#-insert-one-record)

```mysql
INSERT INTO users (name, email, age) VALUES ('Suraj Kumar', 'suraj@example.com', 24);
```

### [🔹 Insert Multiple Records](https://surajkumarjha.me/blog/my-sql-day-1#-insert-multiple-records)

```mysql
INSERT INTO users (name, email, age) VALUES('Karan', 'karan@example.com', 28),('Asha', 'asha@example.com', 32);
```

---

## [🔧 Bonus: UPDATE and DELETE](https://surajkumarjha.me/blog/my-sql-day-1#-bonus-update-and-delete)

### [🔹 Update Records](https://surajkumarjha.me/blog/my-sql-day-1#-update-records)

```mysql
UPDATE users SET age = 25 WHERE name = 'Suraj Kumar';
```

### [🔹 Delete Records](https://surajkumarjha.me/blog/my-sql-day-1#-delete-records)

```mysql
DELETE FROM users WHERE age < 20;
```

---
