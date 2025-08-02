---
tags:
  - java
status: 🟩
---

2025-08-02        18:05

---
### 📚 Queue in Java – Full Guide

A **Queue** is a **FIFO** (First In, First Out) data structure – elements are added at the end and removed from the front. Think of it like a line at a ticket counter.

---

## ✅ 1. **Using `Queue` Interface with `LinkedList`**

The `Queue` is an interface in Java, and **`LinkedList`** is one of its commonly used implementations.

### ➤ Example:

```java
import java.util.LinkedList;
import java.util.Queue;

public class QueueExample {
    public static void main(String[] args) {
        Queue<String> queue = new LinkedList<>();

        // Add elements
        queue.add("Alice");
        queue.add("Bob");
        queue.add("Charlie");

        System.out.println("Queue: " + queue); // [Alice, Bob, Charlie]

        // Peek front element
        System.out.println("Front: " + queue.peek()); // Alice

        // Remove front element
        System.out.println("Removed: " + queue.poll()); // Alice

        // Check size
        System.out.println("Size: " + queue.size()); // 2
    }
}
```

---

## ✅ 2. **Important Queue Methods**

|Method|Description|
|---|---|
|`add(E e)`|Adds to the queue (throws exception on fail)|
|`offer(E e)`|Adds to the queue (returns false on fail)|
|`poll()`|Removes and returns the head or null|
|`remove()`|Removes and throws exception if empty|
|`peek()`|Returns the head or null|
|`element()`|Returns the head or throws exception|
|`isEmpty()`|Checks if queue is empty|

---

## ✅ 3. **Using `ArrayDeque` as Queue (Faster)**

```java
import java.util.ArrayDeque;
import java.util.Queue;

public class ArrayDequeQueue {
    public static void main(String[] args) {
        Queue<Integer> q = new ArrayDeque<>();

        q.offer(1);
        q.offer(2);
        q.offer(3);

        System.out.println("Queue: " + q); // [1, 2, 3]
        System.out.println("Front: " + q.peek()); // 1
        System.out.println("Removed: " + q.poll()); // 1
    }
}
```

---

## 🧠 Queue Use Cases in DSA:

- Level-order traversal (BFS)
    
- Task scheduling
    
- Printers/spoolers
    
- Sliding window problems
    
- Round-robin scheduling
    

---

## ⚠️ Other Queue Types in Java:

|Type|Description|
|---|---|
|`PriorityQueue`|Elements sorted by priority|
|`Deque`|Double-ended queue (can act as stack or queue)|
|`BlockingQueue`|Thread-safe queue for concurrency|

---

Would you like to learn about `PriorityQueue`, `Deque`, or want to solve problems like **"First Non-Repeating Character"** using Queue?

---
