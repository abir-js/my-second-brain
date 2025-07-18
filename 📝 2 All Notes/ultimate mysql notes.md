---
tags: 
status:
---

2025-07-17        12:41

## [Ultimate MySQL Handbook](https://surajkumarjha.me/blog/ultimate-mySql-handbook#ultimate-mysql-handbook)

Welcome to the complete, beginner-to-advanced guide to **MySQL**. This handbook covers everything from installation to powerful SQL features like joins, views, subqueries, triggers, and performance tips.

## [🛠 Installing MySQL](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-installing-mysql)

### [Windows/macOS](https://surajkumarjha.me/blog/ultimate-mySql-handbook#windowsmacos)

1. Download: [MySQL Installer](https://dev.mysql.com/downloads/installer/)
2. Choose **Developer Default**
3. Set a root password
4. Optionally install **MySQL Workbench**

### [Ubuntu/Linux](https://surajkumarjha.me/blog/ultimate-mySql-handbook#ubuntulinux)

```sh
sudo apt updatesudo apt install mysql-serversudo mysql_secure_installationsudo mysql
```

Create a user:

```mysql
CREATE USER 'suraj'@'localhost' IDENTIFIED BY 'password';GRANT ALL PRIVILEGES ON *.* TO 'suraj'@'localhost' WITH GRANT OPTION;FLUSH PRIVILEGES;
```

Login:

```mysql
mysql -u suraj -p
```

## [🧱 MySQL Basics](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-mysql-basics)

### [What is a DBMS?](https://surajkumarjha.me/blog/ultimate-mySql-handbook#what-is-a-dbms)

A **DBMS (Database Management System)** helps you create, retrieve, and manage data.

### [What is a Database?](https://surajkumarjha.me/blog/ultimate-mySql-handbook#what-is-a-database)

Think of a **database** as a folder:

- Each **table** is like a file
- Each **row** is like a record

### [Creating a Database](https://surajkumarjha.me/blog/ultimate-mySql-handbook#creating-a-database)

```mysql
CREATE DATABASE startersql;
USE startersql;
```

### [Creating a Table](https://surajkumarjha.me/blog/ultimate-mySql-handbook#creating-a-table)

```mysql
CREATE TABLE users (  id INT AUTO_INCREMENT PRIMARY KEY,  name VARCHAR(100) NOT NULL,  email VARCHAR(100) UNIQUE NOT NULL,  gender ENUM('Male', 'Female', 'Other'),  date_of_birth DATE,  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP);
```

### [Dropping a Database](https://surajkumarjha.me/blog/ultimate-mySql-handbook#dropping-a-database)

```mysql
DROP DATABASE startersql;
```

## [📦 Data Types](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-data-types)

- `INT`, `DECIMAL(10,2)`
- `VARCHAR(100)`
- `ENUM('Male','Female','Other')`
- `DATE`, `TIMESTAMP`
- `BOOLEAN`

## [🛠 Constraints](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-constraints)

- `PRIMARY KEY`
- `UNIQUE`
- `NOT NULL`
- `DEFAULT`
- `AUTO_INCREMENT`
- `CHECK`

## [📊 CRUD Operations](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-crud-operations)

### [Inserting Data](https://surajkumarjha.me/blog/ultimate-mySql-handbook#inserting-data)

```mysql
INSERT INTO users (name, email, gender, date_of_birth)VALUES ('Alice', 'alice@example.com', 'Female', '1995-05-14');
```

Multiple Rows:

```mysql
INSERT INTO users (name, email, gender, date_of_birth)VALUES('Bob', 'bob@example.com', 'Male', '1990-11-23'),('Charlie', 'charlie@example.com', 'Other', '1988-02-17');
```

### [Selecting Data](https://surajkumarjha.me/blog/ultimate-mySql-handbook#selecting-data)

```mysql
SELECT * FROM users;
SELECT name, email FROM users;
```

With filters:

```mysql
SELECT * FROM users WHERE gender = 'Male';
SELECT * FROM users WHERE date_of_birth BETWEEN '1990-01-01' AND '2000-12-31';
```

## [🥰 Updating & Deleting](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-updating--deleting)

### [Update](https://surajkumarjha.me/blog/ultimate-mySql-handbook#update)

```mysql
UPDATE users SET name = 'Alicia' WHERE id = 1;
UPDATE users SET salary = salary + 10000 WHERE salary < 60000;
```

### [Delete](https://surajkumarjha.me/blog/ultimate-mySql-handbook#delete)

```mysql
DELETE FROM users WHERE id = 3;DELETE FROM users; -- caution!
```

## [🔍 Advanced Queries](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-advanced-queries)

### [Aggregate Functions](https://surajkumarjha.me/blog/ultimate-mySql-handbook#aggregate-functions)

```mysql
SELECT COUNT(*) FROM users;
SELECT AVG(salary), MIN(salary), MAX(salary) FROM users;
```

### [String Functions](https://surajkumarjha.me/blog/ultimate-mySql-handbook#string-functions)

```mysql
SELECT LENGTH(name), UPPER(name), LOWER(name) FROM users;SELECT CONCAT(name, ' <', email, '>') FROM users;
```

### [Date Functions](https://surajkumarjha.me/blog/ultimate-mySql-handbook#date-functions)

```mysql
SELECT NOW(), YEAR(date_of_birth) FROM users;
SELECT TIMESTAMPDIFF(YEAR, date_of_birth, CURDATE()) AS age FROM users;
```

### [Math & Logic](https://surajkumarjha.me/blog/ultimate-mySql-handbook#math--logic)

```mysql
SELECT MOD(id, 2) AS is_even FROM users;SELECT IF(gender = 'Female', 'Yes', 'No') AS is_female FROM users;
```

## [🔄 Transactions](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-transactions)

```mysql
SET autocommit = 0;
UPDATE users SET salary = 80000 WHERE id = 5;
COMMIT;
-- or ROLLBACK;
SET autocommit = 1;
```

## [🔗 Relationships & Joins](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-relationships--joins)

### [Foreign Key](https://surajkumarjha.me/blog/ultimate-mySql-handbook#foreign-key)

```mysql
CREATE TABLE addresses (  id INT AUTO_INCREMENT PRIMARY KEY,  user_id INT,  city VARCHAR(100),  FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE);
```

### [JOINS](https://surajkumarjha.me/blog/ultimate-mySql-handbook#joins)

```mysql
-- INNER JOIN
SELECT users.name, addresses.cityFROM usersINNER JOIN addresses ON users.id = addresses.user_id;
-- LEFT JOIN
SELECT users.name, addresses.cityFROM usersLEFT JOIN addresses ON users.id = addresses.user_id;
```

## [🔀 UNION & SELF JOIN](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-union--self-join)

```mysql
SELECT name FROM usersUNIONSELECT name FROM admin_users;
-- Self Join
SELECT a.name AS user, b.name AS referred_byFROM users aLEFT JOIN users b ON a.referred_by_id = b.id;
```

## [👁 Views](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-views)

```mysql
CREATE VIEW high_salary_users ASSELECT id, name, salary FROM users WHERE salary > 70000;SELECT * FROM high_salary_users;DROP VIEW high_salary_users;
```

## [📊 Indexing](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-indexing)

```mysql
SHOW INDEXES FROM users;
CREATE INDEX idx_email ON users(email);
DROP INDEX idx_email ON users;
```

Multi-column:

```mysql
CREATE INDEX idx_gender_salary ON users(gender, salary);
```

## [🤐 Subqueries](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-subqueries)

```mysql
SELECT name FROM usersWHERE salary > (SELECT AVG(salary) FROM users);
SELECT name, salary,(SELECT AVG(salary) FROM users) AS avg_salaryFROM users;
```

## [📊 GROUP BY & HAVING](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-group-by--having)

```mysql
SELECT gender, AVG(salary) FROM users GROUP BY gender;
SELECT gender, AVG(salary) FROM users GROUP BY gender HAVING AVG(salary) > 75000;
```

## [🔀 Stored Procedures](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-stored-procedures)

```mysql
DELIMITER $$CREATE PROCEDURE AddUser(  IN p_name VARCHAR(100),  IN p_email VARCHAR(100),  IN p_gender ENUM('Male','Female','Other'),  IN p_dob DATE,  IN p_salary INT)BEGIN  INSERT INTO users (name, email, gender, date_of_birth, salary)  VALUES (p_name, p_email, p_gender, p_dob, p_salary);END$$DELIMITER ;CALL AddUser('Kiran Sharma', 'kiran@example.com', 'Female', '1994-06-15', 72000);
```

## [🚨 Triggers](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-triggers)

```mysql
CREATE TABLE user_log (  id INT AUTO_INCREMENT PRIMARY KEY,  user_id INT,  name VARCHAR(100),  created_on TIMESTAMP DEFAULT CURRENT_TIMESTAMP);
DELIMITER $$CREATE TRIGGER after_user_insertAFTER INSERT ON usersFOR EACH ROWBEGIN  INSERT INTO user_log (user_id, name)  VALUES (NEW.id, NEW.name);END$$DELIMITER ;
```

## [🧠 Miscellaneous](https://surajkumarjha.me/blog/ultimate-mySql-handbook#-miscellaneous)

### [Logical Operators](https://surajkumarjha.me/blog/ultimate-mySql-handbook#logical-operators)

- `AND`, `OR`, `NOT`

### [Wildcards](https://surajkumarjha.me/blog/ultimate-mySql-handbook#wildcards)

```mysql
SELECT * FROM users WHERE name LIKE 'A%'; -- starts with A
```

### [DISTINCT](https://surajkumarjha.me/blog/ultimate-mySql-handbook#distinct)

```mysql
SELECT DISTINCT gender FROM users;
```

### [TRUNCATE](https://surajkumarjha.me/blog/ultimate-mySql-handbook#truncate)

```mysql
TRUNCATE TABLE users;
```

### [ALTER](https://surajkumarjha.me/blog/ultimate-mySql-handbook#alter)

```mysql
ALTER TABLE users ADD COLUMN city VARCHAR(100);
ALTER TABLE users CHANGE COLUMN city location VARCHAR(150);
```

---
