---
tags:
  - java
status: 🟩
---

2025-07-27        10:25

---
# Datatypes in java?

### 🟩 1. **Primitive Data Types** (8 types)

| Data Type | Category                              | Size (bits) | Default Value | Min Value                  | Max Value                 |
| --------- | ------------------------------------- | ----------- | ------------- | -------------------------- | ------------------------- |
| `byte`    | Integer                               | 8           | `0`           | -128                       | 127                       |
| `short`   | Integer                               | 16          | `0`           | -32,768                    | 32,767                    |
| `int`     | Integer                               | 32          | `0`           | -2,147,483,648             | 2,147,483,647             |
| `long`    | Integer                               | 64          | `0L`          | -9,223,372,036,854,775,808 | 9,223,372,036,854,775,807 |
| `float`   | Floating pt (~ 7 significant digits)  | 32          | `0.0f`        | ~±1.4E-45                  | ~±3.4028235E+38           |
| `double`  | Floating pt (~ 15 significant digits) | 64          | `0.0d`        | ~±4.9E-324                 | ~±1.7976931348623157E+308 |
| `char`    | Text                                  | 16          | `\u0000`      | 0 (Unicode)                | 65,535 (Unicode)          |
| `boolean` | True/False                            | 1 (logical) | `false`       | `false`                    | `true`                    |



> 🧠 All primitive types are **value types**, and they are **stored in stack memory**.

---

### 🟦 2. **Non-Primitive (Reference) Data Types**

| Data Type   | Description                        | Default Value | Notes                          |
| ----------- | ---------------------------------- | ------------- | ------------------------------ |
| `String`    | Sequence of characters (text)      | `null`        | Immutable; part of `java.lang` |
| `Array`     | Collection of elements (same type) | `null`        | Use `int[]`, `String[]`, etc.  |
| `Class`     | Custom object templates            | `null`        | e.g., `Person`, `Car`          |
| `Interface` | Blueprint for classes              | `null`        | Implemented by classes         |
| `Object`    | Superclass of all classes          | `null`        | Can point to any class object  |

> 🧠 All non-primitive types are **reference types**, and they are **stored in heap memory** (with references in stack).

---

## ✅ Summary

- Use **primitive types** for performance.
    
- Use **non-primitive types** (like `String`, `Array`) for complex structures.
    
- `String`, `Array`, and all objects use **class-based allocation**.
    

---


