---
tags:
  - mysql
status: 🟩
---

2025-07-22        12:25

In **MySQL**, a **composite key** (also called a **composite primary key** or **composite index**) is a **key made up of two or more columns** that together uniquely identify a row in a table.

---

### ✅ Example:

Suppose you have a table for student course enrollment:

```sql
CREATE TABLE enrollments (
    student_id INT,
    course_id INT,
    enrollment_date DATE,
    PRIMARY KEY (student_id, course_id)
);
```

- Here, neither `student_id` nor `course_id` alone is enough to uniquely identify a row.
    
- But **together** (`student_id + course_id`), they make a **composite key** that ensures uniqueness.
    
- This prevents a student from enrolling in the same course more than once.
    

---

### 💡 Characteristics of Composite Keys:

|Feature|Description|
|---|---|
|Uniqueness|Ensures each combination of the key columns is unique.|
|Indexing|MySQL automatically creates an index on composite keys.|
|Leftmost prefix|MySQL can use the **leftmost prefix** of the composite key for queries.|
|Order matters|`PRIMARY KEY (A, B)` is not the same as `PRIMARY KEY (B, A)`.|

---

### 🔍 Leftmost Prefix Rule:

If you define a composite key as:

```sql
PRIMARY KEY (col1, col2, col3)
```

Then MySQL can use the index to efficiently filter by:

- `col1`
    
- `col1, col2`
    
- `col1, col2, col3`
    

But **not** by `col2` alone or `col2, col3` — unless another index is defined.

---
