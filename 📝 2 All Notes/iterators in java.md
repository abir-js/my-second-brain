---
tags:
  - java
  - dsa
status: 🟩
---

2025-08-02        00:23

---
## ✅ What is an `Iterator`?

- `Iterator` is an **interface** in `java.util`.
    
- It provides a **standard way to loop through elements** of a collection **one by one**, regardless of how the collection is implemented (List, Set, etc).
    
- It **replaces the older `Enumeration` interface**.
    

---

### 📦 Import Statement:

```java
import java.util.Iterator;
```

---

## 🧠 Why Use an Iterator?

- To **traverse any collection** (List, Set, etc.)
    
- To **safely remove elements** while iterating  
    ❗ You **cannot remove elements directly using a for-each loop**, but you **can** using `iterator.remove()`.
    

---

## 🔧 Methods of the `Iterator` Interface

| Method      | Description                                              |
| ----------- | -------------------------------------------------------- |
| `hasNext()` | Returns `true` if there are more elements                |
| `next()`    | Returns the next element                                 |
| `remove()`  | Removes the last element returned by `next()` (optional) |

---

## 🧪 Example with `ArrayList`:

```java
import java.util.ArrayList;
import java.util.Iterator;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("A");
        list.add("B");
        list.add("C");

        Iterator<String> it = list.iterator();

        while (it.hasNext()) {
            String value = it.next();
            System.out.println(value);

            // Removing "B" during iteration
            if (value.equals("B")) {
                it.remove(); // ✅ safe to remove while iterating
            }
        }

        System.out.println("After removal: " + list);
    }
}
```

### Output:

```
A
B
C
After removal: [A, C]
```

---

## 🔴 Common Mistake – Don't Do This:

```java
for (String item : list) {
    if (item.equals("B")) {
        list.remove(item); // ❌ ConcurrentModificationException
    }
}
```

✅ Instead, use an iterator if you want to **remove elements while looping**.

---

## 🧩 Where is Iterator used?

You can get an `Iterator` from:

- `List`, `Set`, `Queue`, etc.
    

```java
Iterator<String> it = list.iterator();
```

Even when you do:

```java
for (String s : list)
```

Under the hood, Java is using an `Iterator`.

---

## ✅ Summary

| Feature          | Value                             |
| ---------------- | --------------------------------- |
| Interface        | `Iterator` (from `java.util`)     |
| Purpose          | Traverse collections safely       |
| Key Methods      | `hasNext()`, `next()`, `remove()` |
| Collection types | Works with `List`, `Set`, `Queue` |

---
