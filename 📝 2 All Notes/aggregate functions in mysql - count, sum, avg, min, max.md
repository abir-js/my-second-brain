---
tags:
  - mysql
status: 🟩
---

2025-07-20        11:00

---
# What are aggregate functions in mysql?

Aggregate functions in **MySQL** are used to perform calculations on **multiple rows of a table** and return a **single value**. They are most commonly used with `GROUP BY` and `HAVING` clauses.

---

### ✅ Common Aggregate Functions in MySQL:

|Function|Description|
|---|---|
|`COUNT()`|Returns the number of rows|
|`SUM()`|Returns the total sum of a numeric column|
|`AVG()`|Returns the average value of a numeric column|
|`MIN()`|Returns the smallest value|
|`MAX()`|Returns the largest value|

---

### 📌 Examples:

#### 1. **COUNT()**

```sql
SELECT COUNT(*) AS total_users FROM users;
```

> Counts all rows in the `users` table.

#### 2. **SUM()**

```sql
SELECT SUM(salary) AS total_salary FROM users;
```

> Adds all salaries together.

#### 3. **AVG()**

```sql
SELECT AVG(salary) AS average_salary FROM users;
```

> Calculates the average salary.

#### 4. **MIN() / MAX()**

```sql
SELECT MIN(salary) AS lowest_salary, MAX(salary) AS highest_salary FROM users;
```

> Gets the minimum and maximum salary.

---

### 🎯 With GROUP BY

Group data by a specific column, then apply aggregate function:

```sql
SELECT gender, COUNT(*) AS total FROM users
GROUP BY gender;
```

> Counts how many users are there per gender.

---

### 🔍 With HAVING

`HAVING` is used to filter results **after aggregation**:

```sql
SELECT gender, COUNT(*) AS total FROM users
GROUP BY gender
HAVING total > 1;
```

---

Let me know if you want examples with `JOIN`, `WHERE`, or `subqueries`.

---
