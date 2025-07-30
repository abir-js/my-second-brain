---
tags:
  - java
status: 🟩
---

2025-07-30        21:54

---
### 🔄 Widening Conversion in Java

**Widening conversion** (also called **implicit casting**) is the process where a **smaller data type is automatically converted to a larger data type** by the Java compiler.

---

### ✅ **Order of Widening in Java (Numeric types)**

```
byte → short → int → long → float → double
            ↑
          char
```

---

### 🔹 **Why it’s called “widening”?**

Because you’re **moving to a type that can hold a wider range of values**, so there's **no data loss**, and Java does it automatically.

---

### ✅ **Examples of Widening Conversion:**

```java
public class WideningExample {
    public static void main(String[] args) {
        int a = 100;
        long b = a;       // int to long
        float c = b;      // long to float
        double d = c;     // float to double

        char ch = 'A';
        int code = ch;    // char to int (Unicode value)

        System.out.println("int: " + a);
        System.out.println("long: " + b);
        System.out.println("float: " + c);
        System.out.println("double: " + d);
        System.out.println("char: " + ch + " → code: " + code);
    }
}
```

---

### 🔸 Widening Works:

- **Automatically** (no casting needed)
    
- **Safely** (no precision/data loss)
    

---

### ❌ Narrowing Conversion (opposite of widening):

You need **explicit casting** when going from bigger to smaller type:

```java
double d = 10.5;
int i = (int) d;  // Narrowing → must cast explicitly
```

---

Let me know if you want a **visual diagram**, a quiz, or examples involving **objects and inheritance** (which also use widening).

---
