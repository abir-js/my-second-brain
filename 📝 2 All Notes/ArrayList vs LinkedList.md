---
tags:
  - dsa
  - java
status: 🟩
---

2025-08-02        01:28

---
## 🆚 ArrayList vs LinkedList

### 🔄 Basic Definition

| Feature        | ArrayList                     | LinkedList                          |
| -------------- | ----------------------------- | ----------------------------------- |
| Implementation | Backed by a **dynamic array** | Backed by a **doubly linked list**  |
| Data Storage   | Contiguous memory (array)     | Nodes with references (prev & next) |

---

### ⚡ Performance Comparison

|Operation|ArrayList|LinkedList|
|---|---|---|
|**Access by Index**|🔥 Fast – O(1)|🐢 Slow – O(n)|
|**Insertion at End**|⚡ Fast – O(1) (amortized)|⚡ Fast – O(1)|
|**Insertion at Start**|🐢 Slow – O(n)|⚡ Fast – O(1)|
|**Deletion at Start**|🐢 Slow – O(n)|⚡ Fast – O(1)|
|**Search by Value**|🐢 Slow – O(n)|🐢 Slow – O(n)|

---

### 🛠 Memory & Overhead

| Aspect                | ArrayList                  | LinkedList                              |
| --------------------- | -------------------------- | --------------------------------------- |
| **Memory Efficiency** | Better (no extra pointers) | More memory (2 extra pointers per node) |
| **Cache Performance** | Better                     | Poorer (non-contiguous nodes)           |

---

### ✅ When to Use

|If You Want To...|Use|
|---|---|
|Fast random access (`get(i)`)|`ArrayList`|
|Frequent insertions/deletions at ends or middle|`LinkedList`|
|Memory-efficient collection|`ArrayList`|

---

### 🔍 Example Code

```java
List<Integer> arrayList = new ArrayList<>();
List<Integer> linkedList = new LinkedList<>();
```

---

### 🧠 Conclusion

|Verdict|
|---|
|Use `ArrayList` for **most cases**, especially if you access elements frequently by index.|
|Use `LinkedList` when you frequently **insert/remove elements at the beginning or middle**.|

---
