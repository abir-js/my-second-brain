---
tags:
  - java
status: 🟩
---

2025-08-03        10:17

---
### 🔹 `HashSet` in Java

A **`HashSet`** is a part of the **Java Collections Framework** and implements the **`Set`** interface using a **hash table**. It **does not allow duplicate elements**, and it **does not maintain insertion order**.

---

### ✅ Key Features of `HashSet`

- **No duplicates** allowed.
    
- **Unordered** (insertion order is not preserved).
    
- **At most one `null`** element is allowed.
    
- Internally backed by a **`HashMap`**.
    
- Average time complexity:
    
    - `add()`, `remove()`, `contains()` – **O(1)**
        

---

### 🔰 Syntax:

```java
HashSet<Type> setName = new HashSet<>();
```

---

### 🧪 Example:

```java
import java.util.HashSet;

public class HashSetExample {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();

        set.add("Apple");
        set.add("Banana");
        set.add("Orange");
        set.add("Apple"); // Duplicate, will be ignored
        set.add(null);    // Allowed once

        System.out.println(set); // Output may vary in order
    }
}
```

---

### 🧠 Common Methods in `HashSet`

|Method|Description|
|---|---|
|`add(E e)`|Adds an element|
|`remove(Object o)`|Removes the specified element|
|`contains(Object o)`|Returns `true` if element exists|
|`size()`|Number of elements in the set|
|`isEmpty()`|Checks if set is empty|
|`clear()`|Removes all elements|
|`iterator()`|Returns an iterator|

---

### ⚠️ Important Notes

- **Duplicates are ignored** silently.
    
- **Null is allowed**, but only once.
    
- If you need **insertion order**, use `LinkedHashSet`.
    
- If you need **sorted order**, use `TreeSet`.
    

---

### 🔄 Example: Iterating Over a HashSet

```java
for (String item : set) {
    System.out.println(item);
}
```

---

Would you like a visual comparison of `HashSet`, `LinkedHashSet`, and `TreeSet`?

---
