---
tags:
  - java
status: 🟩
---

2025-08-03        00:35

---
### 📚 `ArrayDeque` in Java – Complete Guide

`ArrayDeque` (Array Double Ended Queue) is a **resizable-array implementation** of the `Deque` interface in Java. It is faster than `Stack`, `LinkedList`, and traditional `Queue` for most use cases.

---

## ✅ Why Use `ArrayDeque`?

|Feature|Details|
|---|---|
|Implements|`Deque<E>`, `Queue<E>`|
|Allows null?|❌ No (throws `NullPointerException`)|
|Thread-safe?|❌ No (use externally synchronized if needed)|
|Performance|✅ Fast for add/remove from both ends|
|Backed by|A dynamic array (not linked list)|

---

## ✅ 1. **Basic Example**

```java
import java.util.ArrayDeque;

public class ArrayDequeExample {
    public static void main(String[] args) {
        ArrayDeque<String> deque = new ArrayDeque<>();

        // Add elements to the end
        deque.add("A");
        deque.add("B");
        deque.add("C");

        System.out.println("Deque: " + deque); // [A, B, C]

        // Remove from front
        System.out.println("Removed: " + deque.remove()); // A

        // Add to front
        deque.addFirst("X");

        // Add to back
        deque.addLast("Y");

        System.out.println("Deque after operations: " + deque); // [X, B, C, Y]
    }
}
```

---

## ✅ 2. **Important Methods**

|Method|Description|
|---|---|
|`addFirst(e)`|Adds element to the front|
|`addLast(e)`|Adds element to the back|
|`removeFirst()`|Removes and returns front element|
|`removeLast()`|Removes and returns last element|
|`peekFirst()`|Returns front element without removing|
|`peekLast()`|Returns last element without removing|
|`offerFirst(e)`|Adds to front, returns `true/false`|
|`offerLast(e)`|Adds to back, returns `true/false`|
|`pop()`|Pops from front (stack behavior)|
|`push(e)`|Pushes to front (stack behavior)|

---

## 🔄 Acts Like Both Stack and Queue

### 🟢 As **Queue (FIFO)**:

```java
deque.offer(1);     // add to back
deque.poll();       // remove from front
```

### 🔴 As **Stack (LIFO)**:

```java
deque.push(1);      // add to front
deque.pop();        // remove from front
```

---

## 🧠 Use Cases

- Implementing **stack** and **queue** in one structure
    
- **Palindrome check**
    
- **Sliding window maximum**
    
- Browser **forward/back navigation**
    
- Tree traversal (e.g. level-order)
    

---

## ⚠️ Notes

- Better than `Stack` and `LinkedList` in most cases (faster, less overhead)
    
- Still not thread-safe (use `Collections.synchronizedDeque()` if needed)
    

---

Want to see real problems like **LRU Cache**, **Palindrome check**, or **Sliding Window Maximum** using `ArrayDeque`?

---
