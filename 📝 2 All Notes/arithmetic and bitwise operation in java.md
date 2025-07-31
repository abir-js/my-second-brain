---
tags:
  - java
status: 🟩
---

2025-07-31        10:24

---
## ➕ 1. **Arithmetic Operators**

These are used for performing **basic mathematical operations**.

|Operator|Name|Example (`a = 10`, `b = 3`)|Result|
|---|---|---|---|
|`+`|Addition|`a + b`|`13`|
|`-`|Subtraction|`a - b`|`7`|
|`*`|Multiplication|`a * b`|`30`|
|`/`|Division|`a / b`|`3` (int div)|
|`%`|Modulus (remainder)|`a % b`|`1`|

### ✅ Example:

```java
int a = 10, b = 3;
System.out.println(a + b); // 13
System.out.println(a / b); // 3 (no decimals in int division)
```

---

## 🧮 2. **Bitwise Operators**

These work on the **bit level** (binary representation of numbers).

|Operator|Name|Example (`a = 5`, `b = 3`)|Binary Operation|Result|
|---|---|---|---|---|
|`&`|AND|`a & b`|`0101 & 0011 = 0001`|`1`|
|`|`|OR|`a|b`|
|`^`|XOR|`a ^ b`|`0101 ^ 0011 = 0110`|`6`|
|`~`|NOT (1's complement)|`~a`|`~0101 = 1010`|`-6`|
|`<<`|Left shift|`a << 1`|`0101 → 1010`|`10`|
|`>>`|Right shift|`a >> 1`|`0101 → 0010`|`2`|
|`>>>`|Unsigned right shift|`-5 >>> 1`|Logical shift right|JVM-dep|

---

### ✅ Bitwise Example:

```java
public class BitwiseExample {
    public static void main(String[] args) {
        int a = 5;  // 0101
        int b = 3;  // 0011

        System.out.println("a & b = " + (a & b));  // 1
        System.out.println("a | b = " + (a | b));  // 7
        System.out.println("a ^ b = " + (a ^ b));  // 6
        System.out.println("~a = " + (~a));        // -6
        System.out.println("a << 1 = " + (a << 1)); // 10
        System.out.println("a >> 1 = " + (a >> 1)); // 2
    }
}
```

---

### ⚠️ Note on `~a`:

- In Java, integers are 32-bit signed.
    
- So `~a` is `-a - 1`.
    

---

Would you like:

- a visual binary table of operations?
    
- a quiz for practice?
    
- or examples mixing both arithmetic and bitwise together?

---
