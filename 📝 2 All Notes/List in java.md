---
tags:
  - dsa
  - java
status: 🟩
---

2025-08-02        00:12

---
## ✅ What is `List` in Java?

- `List` is an **interface** in `java.util` package.
    
- It **extends** the `Collection` interface.
    
- Represents an **ordered collection** (a **sequence**) of elements.
    
- Allows:
    
    - **Duplicate elements**
        
    - **Index-based access**
        
    - **Insertion order** to be maintained
        

---

### 📦 Import Statement:

```java
import java.util.List;
```

Or use the wildcard:

```java
import java.util.*;
```

---

## 🧠 Common Implementations of `List`:

|Class|Description|
|---|---|
|`ArrayList`|Resizable array; fast access, slow insertion|
|`LinkedList`|Doubly linked list; fast insertion/removal|
|`Vector`|Synchronized (legacy) array|
|`Stack`|Subclass of Vector; LIFO behavior|

---

## 🧪 Example:

```java
import java.util.List;
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        List<String> names = new ArrayList<>();

        names.add("Alice");
        names.add("Bob");
        names.add("Alice");  // Duplicates allowed

        System.out.println(names.get(0));     // Alice
        System.out.println(names.contains("Bob")); // true
        names.remove("Alice"); // Removes first "Alice"

        for (String name : names) {
            System.out.println(name);
        }
    }
}
```

---

## 🚀 Key Methods of `List` Interface

|Method|Description|
|---|---|
|`add(E e)`|Adds element|
|`add(int index, E e)`|Inserts element at index|
|`get(int index)`|Returns element at index|
|`set(int index, E e)`|Replaces element at index|
|`remove(int index)`|Removes element at index|
|`indexOf(Object o)`|Returns first index of element|
|`lastIndexOf(Object o)`|Returns last index of element|
|`subList(from, to)`|Returns a view of the specified range|
|`size()`|Returns number of elements|

---

## 📊 Summary

|Feature|Description|
|---|---|
|Type|Interface|
|Package|`java.util`|
|Maintains order|✅ Yes|
|Allows duplicates|✅ Yes|
|Access by index|✅ Yes (`get(int index)`)|
|Most common impl.|`ArrayList`, `LinkedList`|

---

## 📌 Note

You often write:

```java
List<String> list = new ArrayList<>();
```

Why?

- You **program to the interface** (`List`) but **instantiate the class** (`ArrayList`).
    
- This makes your code **more flexible and loosely coupled**.
    

---

Would you like to see how `List` compares with `Set` or `Map`, or how to use it with custom classes?

---
