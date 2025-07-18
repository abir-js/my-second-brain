---
tags:
  - mysql
status: 🟩
---

2025-07-17        20:44

# Datatypes in mysql

### 1. CHAR (size)

- Char is used for **fixed length character** strings. 
- When you define a CHAR column, you must specify a fixed length for the string, e.g., `CHAR(10)`. 
- If you store a shorter string in a `CHAR(10)` column, it will be padded with spaces to fill the fixed length.

### 2. VARCHAR (size)

- VARCHAR is used for **variable length character** strings. 
- When you define a VARCHAR column, you must specify a fixed length for the string, e.g., `CHAR(255)`. 
- The actual storage size of the string is the length of the data plus one byte to store the length pf the data.
- That means 

### 3. INT 

- INT is used to store numbers (integers) without decimal points.

### 3. DECIMAL

- DECIMAL datatype is used to store **exact numeric values**.
- It is commonly used for monetary or other values where precision is required,
- The DECIMAL datatype requires two parameters: DECIMAL(p, s), where p specifies the total number of digits that can be stored (precision), and s specifies the number of digits after the decimal point (scale).

### 4. DATE

- Stores a date value in the format **'YYYY-MM-DD'**.
- For example, '2025-03-05'

### 5. Time

- Stores a date value in the format **'HH:MM:SS'**.
- For example, '14:30:00'.

### 4. DATETIME

- Stores a date value in the format **'YYYY-MM-DD HH:MM:SS'**.
- For example, '2025-03-05'


---
