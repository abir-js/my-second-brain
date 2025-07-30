---
tags:
  - java
status: 🟩
---

2025-07-30        21:57

---
### 🔽 Narrowing Conversion in Java (also called **Explicit Type Casting**)

**Narrowing conversion** is when you convert a **larger data type into a smaller data type**. Since there is **potential for data loss**, Java requires you to **explicitly cast** the value.

---

### ✅ **Narrowing Conversion Syntax:**

```java
targetType variable = (targetType) value;
```

---

### 🔹 **Order of Narrowing:**

```
double → float → long → int → char → short → byte
```

---

### ✅ **Example:**

```java
public class NarrowingExample {
    public static void main(String[] args) {
        double d = 99.99;
        int i = (int) d;     // Explicit cast from double to int (decimal part lost)
        byte b = (byte) i;   // int to byte (might lose data if > 127)

        System.out.println("double: " + d);
        System.out.println("int: " + i);
        System.out.println("byte: " + b);
    }
}
```

**Output:**

```
double: 99.99
int: 99
byte: 99
```

---

### ⚠️ Possible Issues with Narrowing:

1. **Precision Loss** (e.g., decimal part is lost)
    
2. **Overflow or Underflow** (value may wrap around if it doesn’t fit)
    

#### Example of data loss:

```java
int i = 300;
byte b = (byte) i;
System.out.println(b);  // Output: 44 (because byte range is -128 to 127)
```

---

### 🔁 Summary Table:

|Conversion Type|Example|Automatic?|Data Loss Risk?|
|---|---|---|---|
|Widening|`int → long`|✅ Yes|❌ No|
|Narrowing|`double → int`|❌ No|✅ Yes|

---

Let me know if you want a visual diagram or a chart showing all primitive data types with their ranges and default values!

---
