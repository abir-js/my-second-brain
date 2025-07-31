---
tags:
  - java
status: 🟩
---

2025-07-30        22:00

---
### 🔤 Strings in Java – Complete Overview

In Java, **strings** are objects that represent sequences of characters. They are widely used and have **built-in support via the `String` class** in the `java.lang` package. **We create objects of `String` class.**

---

## 🧱 1. **Declaring Strings**

```java
String s1 = "Hello";             // Using string literal
String s2 = new String("World"); // Using `new` keyword
```

**Summary:**

- String literals → string pool (heap area), reused.
- `new String()` → new object in heap, not in pool.
- References → stack.
- Stack never stores the actual string object, only references.

---

## 📌 2. **Important Features**

- **Immutable**: Once created, the value of a `String` cannot be changed.
    
- **Stored in String Constant Pool** (for literals) to save memory.
    

---

## 🔍 3. **Common String Methods**

|Method|Description|
|---|---|
|`length()`|Returns length of the string|
|`charAt(int)`|Returns char at specified index|
|`substring(int, int)`|Extracts part of the string|
|`equals(String)`|Compares content (case-sensitive)|
|`equalsIgnoreCase()`|Compares ignoring case|
|`compareTo()`|Lexicographical comparison|
|`contains(String)`|Checks if a substring exists|
|`indexOf(String)`|Returns index of substring|
|`toUpperCase()`|Converts to uppercase|
|`toLowerCase()`|Converts to lowercase|
|`trim()`|Removes leading/trailing spaces|
|`replace(a, b)`|Replaces characters or substrings|
|`split(regex)`|Splits string into array based on delimiter|
|`isEmpty()`|Returns true if length is 0|

---

## 🔁 4. **Example:**

```java
public class StringExample {
    public static void main(String[] args) {
        String name = "Java Programming";

        System.out.println("Length: " + name.length());
        System.out.println("Char at 5: " + name.charAt(5));
        System.out.println("Substring: " + name.substring(5, 16));
        System.out.println("Uppercase: " + name.toUpperCase());
        System.out.println("Contains 'Pro': " + name.contains("Pro"));
    }
}
```

---

## ⚖️ 5. **String Comparison**

```java
String a = "Hello";
String b = "Hello";
String c = new String("Hello");

System.out.println(a == b);       // true (same object from string pool)
System.out.println(a == c);       // false (different objects)
System.out.println(a.equals(c));  // true (same content)
```

---

## 🧠 6. **String Immutability Example**

```java
String s = "Hello";
s.concat(" World");
System.out.println(s); // Output: Hello (not changed)

s = s.concat(" World");
System.out.println(s); // Output: Hello World (new object assigned)
```

---

## 🧰 7. **Mutable Alternatives**

Java provides two mutable string classes:

- `StringBuilder` – Faster, not thread-safe
    
- `StringBuffer` – Thread-safe (synchronized)
    

---

Would you like:

- a comparison between `String`, `StringBuilder`, and `StringBuffer`?
    
- a table of string methods with examples?
    
- or a mini project using string manipulation?

---
