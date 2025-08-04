---
tags:
  - java
status: 🟩
---

2025-08-03        22:01

---
### 📌 HashMap in Java – A Complete Guide

`HashMap` is part of Java's **Collection Framework** and resides in the `java.util` package. It stores data in **key-value pairs**, where each key is unique, and values can be duplicated.

---

### 🔧 Declaration:

```java
import java.util.HashMap;

HashMap<KeyType, ValueType> map = new HashMap<>();
```

Example:

```java
HashMap<String, Integer> studentMarks = new HashMap<>();
```

---

### 📦 Key Features:

|Feature|Description|
|---|---|
|Stores key-value|Each element is stored as a pair.|
|Allows null|One `null` key and multiple `null` values.|
|No order guarantee|Not ordered or sorted.|
|Non-synchronized|Not thread-safe by default.|

---

### 🛠️ Common Methods:

|Method|Description|
|---|---|
|`put(K key, V value)`|Adds a key-value pair|
|`get(Object key)`|Returns value for a key|
|`remove(Object key)`|Removes a key-value pair|
|`containsKey(Object key)`|Checks if key exists|
|`containsValue(Object value)`|Checks if value exists|
|`isEmpty()`|Checks if map is empty|
|`size()`|Returns the number of entries|
|`clear()`|Removes all entries|
|`keySet()`|Returns a `Set` of keys|
|`values()`|Returns a `Collection` of values|
|`entrySet()`|Returns a `Set` of key-value pairs|

---

### 🧪 Example Code:

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<String, Integer> studentMarks = new HashMap<>();

        // Adding entries
        studentMarks.put("Alice", 85);
        studentMarks.put("Bob", 92);
        studentMarks.put("Charlie", 77);

        // Accessing value
        System.out.println("Alice's marks: " + studentMarks.get("Alice"));

        // Removing entry
        studentMarks.remove("Charlie");

        // Checking key existence
        if (studentMarks.containsKey("Bob")) {
            System.out.println("Bob is present.");
        }

        // Iterating through the map
        for (String name : studentMarks.keySet()) {
            System.out.println(name + " => " + studentMarks.get(name));
        }
    }
}
```

---

### 💡 Internal Working:

- Uses a **hash table**.
    
- Calculates the hash of the key using `hashCode()`.
    
- Maps it to a **bucket** (array index).
    
- Handles collisions using **LinkedList** (or Tree in case of large collisions).
    

---

### 🔐 HashMap vs Hashtable vs LinkedHashMap vs TreeMap:

|Feature|HashMap|Hashtable|LinkedHashMap|TreeMap|
|---|---|---|---|---|
|Thread-safe|❌|✅|❌|❌|
|Maintains order|❌|❌|✅ (insertion)|✅ (sorted)|
|Null key/value|1 key, many values|❌|1 key, many values|❌ (no null key)|
|Performance|✅ Fast|Slower|✅|Slower|

---

Let me know if you want visual representation (diagram), real-world examples, or differences with `HashSet`!

---
