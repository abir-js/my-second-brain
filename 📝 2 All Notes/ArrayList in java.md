---
tags:
  - dsa
  - java
status: 🟩
---

2025-08-01        23:58

---
## ✅ What is `ArrayList`?

- `ArrayList` is a **resizable array** implementation of the `List` interface.
    
- Unlike regular arrays, `ArrayList` can **grow or shrink in size dynamically**.
    
- It maintains the **insertion order** and allows **duplicate elements**.
    

```java
import java.util.ArrayList;
```

---

## 🧠 Key Features

|Feature|Description|
|---|---|
|Type|Class (`java.util.ArrayList`)|
|Implements|`List`, `Collection`, `Iterable`|
|Allows duplicates|✅ Yes|
|Maintains order|✅ Yes (insertion order)|
|Index-based access|✅ Yes (like an array)|
|Thread-safe|❌ No (use `Collections.synchronizedList()` for that)|

---

## 🧪 Basic Example

```java
import java.util.ArrayList;

public class Example {
    public static void main(String[] args) {
        ArrayList<String> fruits = new ArrayList<>();

        // Add elements
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Mango");

        // Access by index
        System.out.println(fruits.get(1));  // Output: Banana

        // Remove element
        fruits.remove("Apple");

        // Size
        System.out.println(fruits.size());  // Output: 2

        // Loop through elements
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
    }
}
```

---

## 🧱 Constructor Variants

```java
ArrayList<E> list = new ArrayList<>();
ArrayList<E> list = new ArrayList<>(int initialCapacity);
ArrayList<E> list = new ArrayList<>(Collection<? extends E> c);
```

---

## 🚀 Common Methods

|Method|Description|
|---|---|
|`add(E e)`|Adds element|
|`add(int index, E e)`|Adds at specific index|
|`get(int index)`|Returns element at index|
|`set(int index, E e)`|Replaces element|
|`remove(int index)`|Removes element at index|
|`remove(Object o)`|Removes first occurrence|
|`contains(Object o)`|Returns `true` if exists|
|`size()`|Returns number of elements|
|`clear()`|Removes all elements|
|`isEmpty()`|Checks if empty|

---

## 📦 Internal Working

- Internally uses a **dynamic array**.
    
- Default capacity is **10**.
    
- When full, capacity increases by **50%** (in Java 8+).
    

---

## ❗ Performance

|Operation|Time Complexity|
|---|---|
|Access by index|O(1)|
|Insert/remove at end|O(1) amortized|
|Insert/remove in middle|O(n)|
|Search|O(n)|

---

Would you like to see:

- How `ArrayList` compares with `LinkedList`?
    
- How to use `ArrayList` with custom objects (like classes)?
    
- JavaScript version of the same behavior?

---
