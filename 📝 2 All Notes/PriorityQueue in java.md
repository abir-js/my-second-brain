---
tags:
  - java
status:
---

2025-08-02        23:50

---
### 📚 `PriorityQueue` in Java – Complete Guide

A **`PriorityQueue`** is a special type of queue where **elements are ordered by priority**, not by insertion order.

By default, **the smallest element comes first** (min-heap behavior), but you can customize it using a **comparator**.

---

## ✅ 1. **Import and Basic Usage**

```java
import java.util.PriorityQueue;

public class PriorityQueueExample {
    public static void main(String[] args) {
        PriorityQueue<Integer> pq = new PriorityQueue<>();

        pq.add(30);
        pq.add(10);
        pq.add(20);

        System.out.println("PriorityQueue: " + pq); // Output order not guaranteed

        while (!pq.isEmpty()) {
            System.out.println(pq.poll()); // Output: 10, 20, 30
        }
    }
}
```

---

## ✅ 2. **Key Properties**

|Feature|Description|
|---|---|
|Implements|`Queue` interface|
|Underlying structure|Min-heap (binary heap using array)|
|Default order|Natural order (`Comparable`) – smallest first|
|Allows duplicates|✅ Yes|
|Thread-safe|❌ No (use `PriorityBlockingQueue` for concurrency)|

---

## ✅ 3. **Custom Comparator**

### ➤ Max-Heap:

```java
import java.util.*;

public class MaxHeapExample {
    public static void main(String[] args) {
        PriorityQueue<Integer> maxHeap = new PriorityQueue<>(Collections.reverseOrder());

        maxHeap.add(10);
        maxHeap.add(5);
        maxHeap.add(20);

        while (!maxHeap.isEmpty()) {
            System.out.println(maxHeap.poll()); // 20, 10, 5
        }
    }
}
```

---

### ➤ Custom Class Example (Sort by age)

```java
import java.util.*;

class Person {
    String name;
    int age;
    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public String toString() {
        return name + " (" + age + ")";
    }
}

public class CustomComparatorPQ {
    public static void main(String[] args) {
        PriorityQueue<Person> pq = new PriorityQueue<>(Comparator.comparingInt(p -> p.age));

        pq.add(new Person("Alice", 30));
        pq.add(new Person("Bob", 25));
        pq.add(new Person("Charlie", 28));

        while (!pq.isEmpty()) {
            System.out.println(pq.poll()); // Bob, Charlie, Alice
        }
    }
}
```

---

## 🧠 Use Cases of PriorityQueue

- Dijkstra’s algorithm (shortest path)
    
- A* pathfinding
    
- Task scheduling
    
- Huffman coding
    
- Anytime you need elements processed in order of importance or weight
    

---

## ⚠️ Notes

- Iterating over a `PriorityQueue` **does not guarantee sorted order**.
    
- To get sorted results, **poll repeatedly**.
    

---

Would you like to practice problems using `PriorityQueue` like:

- **K largest/smallest elements**
    
- **Merge k sorted lists**
    
- **Top K frequent words**?
    

Let me know!

---
