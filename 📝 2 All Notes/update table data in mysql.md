---
tags:
  - mysql
status: 🟩
---

2025-07-19        09:38

# What is Title?

```mysql
UPDATE table_name
SET column1 = value1, column2 = value2...
WHERE condition;
```

- **table_name**
	- The name of the table you want to update
	
- **columns**
	- the columns you want to update
	
- **values**
	- the new values you want to set for the columns
	
- **condition**
	- The condition that specifies which rows to update. 
	- If omitted, all rows will be updated

### Example:

```mysql
UPDATE users
SET age = 30
WHERE id = 1
```

---
