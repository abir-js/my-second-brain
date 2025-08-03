---
tags:
  - java
status: 🟩
---

2025-08-03        10:13

---
In Java, a **`Set`** is a **collection that contains no duplicate elements**. It is part of the **Java Collections Framework** and is defined in the `java.util` package.

---

### ✅ **Key Features of Set**

- No duplicate elements allowed.
    
- Unordered (depending on the implementation).
    
- At most one null element (in some implementations).
    

---

### 🔰 **Types of Set in Java**

|Set Type|Ordered?|Allows Null?|Backed By|Use Case|
|---|---|---|---|---|
|`HashSet`|❌ No|✅ One null|Hash table|Fast operations, no order needed|
|`LinkedHashSet`|✅ Yes|✅ One null|Hash table + Linked List|Preserves insertion order|
|`TreeSet`|✅ Sorted|❌ No null|Red-Black tree|Automatically sorted elements (natural/custom order)|

---

### 🧪 **Example: Using `HashSet`**

```java
import java.util.*;

public class SetExample {
    public static void main(String[] args) {
        Set<String> fruits = new HashSet<>();

        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");
        fruits.add("Apple"); // duplicate, will be ignored

        System.out.println(fruits); // No duplicates, no order guaranteed
    }
}
```

---

### 🧠 **Common Methods in Set**

|Method|Description|
|---|---|
|`add(element)`|Adds an element if it's not already present|
|`remove(element)`|Removes an element|
|`contains(element)`|Checks if an element is present|
|`size()`|Returns number of elements|
|`clear()`|Removes all elements|
|`isEmpty()`|Checks if the set is empty|
|`iterator()`|Used for traversing elements|

---

### 📌 **Use Cases**

- Remove duplicates from a collection.
    
- Store unique elements like user IDs, tags, email addresses.
    
- Efficient membership testing (`contains()` is fast in `HashSet`).
    

---

If you want a quick table comparing `List`, `Set`, and `Map`, let me know!

---
