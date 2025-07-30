---
tags:
  - java
status: 🟩
---

2025-07-30        21:51

---
In Java, **ASCII** and **Unicode** are both used to represent character values. Here's a clear breakdown:

---

### ✅ **1. ASCII in Java**

**ASCII** (American Standard Code for Information Interchange) is a **7-bit character set**, meaning it represents **128 characters** (values from `0 to 127`).

In Java:

- ASCII is a **subset** of Unicode.
    
- Java `char` type can represent ASCII characters easily.
    

#### Example:

```java
public class AsciiExample {
    public static void main(String[] args) {
        char ch = 'A';              // Character
        int ascii = (int) ch;       // Get ASCII value
        System.out.println("ASCII value of " + ch + " is: " + ascii);
    }
}
```

**Output:**

```
ASCII value of A is: 65
```

---

### ✅ **2. Unicode in Java**

**Unicode** is a universal character encoding standard that covers **all characters** from all languages (over 1 million possible code points).  
Java uses **Unicode (UTF-16)** for its internal character representation.

- Java `char` is **16-bit**, so it can represent Unicode values from `\u0000` to `\uFFFF` (0 to 65,535).
    
- Unicode characters beyond `\uFFFF` are represented using **surrogate pairs**.
    

#### Example:

```java
public class UnicodeExample {
    public static void main(String[] args) {
        char ch = '\u0906';  // Unicode for 'आ' (Devanagari)
        System.out.println("Character: " + ch);
    }
}
```

**Output:**

```
Character: आ
```

---

### ✅ Print All ASCII Characters in Java

```java
public class PrintAscii {
    public static void main(String[] args) {
        for (int i = 0; i <= 127; i++) {
            System.out.println(i + " : " + (char) i);
        }
    }
}
```

---

### 🔎 Summary

|Aspect|ASCII|Unicode|
|---|---|---|
|Size|7 bits (128 characters)|Variable (Java uses 16-bit UTF-16)|
|Java `char`|Can represent ASCII characters|Represents Unicode characters|
|Range|0 to 127|0 to 65,535 (`char`)|
|Example|`'A'` is 65|`'\u0906'` is 'आ'|

Let me know if you want a table of ASCII codes in Java or a Unicode character map viewer.

---
