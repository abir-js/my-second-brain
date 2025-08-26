---
tags:
  - dsa
  - java
status: 🟩
---

2025-08-02        01:09

---
## ✅ What is `LinkedList` in Java?

- `LinkedList` is a **class** in Java that implements both:
    
    - `List` interface (so it’s like an `ArrayList`)
        
    - `Deque` interface (so it can be used as a queue or stack)
        
- It is a **doubly linked list**, meaning each node points to both the next and previous node.
    
- Belongs to the package: `java.util`
    

---

### 📦 Import Statement:

```java
import java.util.LinkedList;
```

---

## 🧠 Key Features of `LinkedList`

|Feature|Description|
|---|---|
|Implements|`List`, `Deque`, `Queue`|
|Allows duplicates|✅ Yes|
|Maintains order|✅ Yes (insertion order)|
|Null values allowed|✅ Yes|
|Random access|❌ No (unlike `ArrayList`)|
|Insert/delete in middle|✅ Fast (better than `ArrayList`)|

---

## 🧪 Example

```java
import java.util.LinkedList;

public class Main {
    public static void main(String[] args) {
        LinkedList<String> cities = new LinkedList<>();

        cities.add("Delhi");
        cities.add("Mumbai");
        cities.addFirst("Kolkata");  // Insert at front
        cities.addLast("Chennai");  // Insert at end

        System.out.println(cities); // [Kolkata, Delhi, Mumbai, Chennai]

        cities.remove("Delhi");
        System.out.println("After removal: " + cities);
    }
}
```

---

## 🚀 Common Methods

|Method|Description|
|---|---|
|`add()`|Adds to end|
|`addFirst()`|Adds to front|
|`addLast()`|Adds to end|
|`remove()`|Removes first element|
|`removeFirst()`|Removes from front|
|`removeLast()`|Removes from end|
|`getFirst()`|Gets first element|
|`getLast()`|Gets last element|
|`size()`|Returns number of elements|

---

## 🆚 ArrayList vs LinkedList

|Feature|`ArrayList`|`LinkedList`|
|---|---|---|
|Backed by|Dynamic Array|Doubly Linked List|
|Access speed|🔼 Fast (O(1))|🔽 Slow (O(n))|
|Insert/delete|🔽 Slow (shifting required)|🔼 Fast (just change links)|
|Memory usage|Less|More (extra pointers)|

---

## 🔧 Use Cases

Use `LinkedList` when:

- You need to frequently add/remove from **beginning or middle**.
    
- You need **queue**, **deque**, or **stack-like** behavior.
    

---

### ✅ Example as a Queue:

```java
LinkedList<Integer> queue = new LinkedList<>();
queue.add(1);         // enqueue
queue.add(2);
System.out.println(queue.remove()); // dequeue → 1
```

---

### ✅ Example as a Stack:

```java
LinkedList<Integer> stack = new LinkedList<>();
stack.push(10);
stack.push(20);
System.out.println(stack.pop());  // 20
```

---

## 📦 Summary

|Property|Value|
|---|---|
|Class|`LinkedList<E>` in `java.util`|
|Implements|`List`, `Deque`, `Queue`|
|Allows Duplicates|✅ Yes|
|Best For|Frequent insertions/deletions|
|Not Best For|Random access|

---

Would you like a diagram to visualize how the `LinkedList` nodes are connected?

---
