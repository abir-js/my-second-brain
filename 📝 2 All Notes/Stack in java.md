---
tags:
  - java
status: 🟩
---

2025-08-02        17:51

---
### 📚 Stack in Java – Complete Guide

A **Stack** is a **LIFO** (Last In, First Out) data structure. Think of it like a stack of plates – you add (push) on top and remove (pop) from the top.

---

## ✅ 1. **Using Java’s Built-in Stack Class**

Java provides a `Stack` class in `java.util` package.

### ➤ Example:

```java
import java.util.Stack;

public class StackExample {
    public static void main(String[] args) {
        Stack<Integer> stack = new Stack<>();

        // Push elements
        stack.push(10);
        stack.push(20);
        stack.push(30);

        System.out.println("Stack: " + stack); // [10, 20, 30]

        // Peek top element
        System.out.println("Top: " + stack.peek()); // 30

        // Pop element
        System.out.println("Popped: " + stack.pop()); // 30

        // Check if empty
        System.out.println("Is Empty? " + stack.isEmpty()); // false

        // Search (1-based index from top)
        System.out.println("Position of 10: " + stack.search(10)); // 2
    }
}
```

---

## ✅ 2. **Important Stack Methods**

|Method|Description|
|---|---|
|`push(E e)`|Pushes an item onto the top|
|`pop()`|Removes and returns the top item|
|`peek()`|Returns the top item without removing|
|`isEmpty()`|Checks if stack is empty|
|`search(E e)`|Finds position from top (1-based)|

---

## ⚠️ Note:

`Stack` is a legacy class (extends `Vector`) — for production code, Java devs prefer using:

### ✅ **Deque as Stack (Recommended)**

```java
import java.util.ArrayDeque;
import java.util.Deque;

public class DequeStackExample {
    public static void main(String[] args) {
        Deque<Integer> stack = new ArrayDeque<>();

        stack.push(1); // push
        stack.push(2);
        stack.push(3);

        System.out.println("Top: " + stack.peek()); // 3
        System.out.println("Popped: " + stack.pop()); // 3
    }
}
```

---

## 🧠 Stack Use Cases in DSA:

- Balanced parentheses
    
- Undo/Redo operations
    
- Function call stack
    
- Depth-First Search (DFS)
    
- Expression evaluation
    

---

Want a visual or code challenge for practicing stack problems?

---
