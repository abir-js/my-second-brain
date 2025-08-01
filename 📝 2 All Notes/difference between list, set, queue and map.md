---
tags:
  - java
  - dsa
status: 🟩
---

2025-08-01        21:03

---
Here’s a clear **comparison table** showing the **difference between `List`, `Set`, `Queue`, and `Map`** in Java:

|Feature / Collection|`List`|`Set`|`Queue`|`Map`|
|---|---|---|---|---|
|**Package**|`java.util`|`java.util`|`java.util`|`java.util`|
|**Implements**|`Collection`|`Collection`|`Collection`|**Not** a `Collection`, separate interface|
|**Duplicates**|✅ **Allows duplicates**|❌ **No duplicates allowed**|✅ May allow duplicates|✅ **Keys** ❌, **Values** ✅|
|**Ordering**|Maintains insertion order|❌ Unordered (e.g. `HashSet`)|Order depends on type|No order (e.g. `HashMap`), but `LinkedHashMap` preserves it|
|**Index-based access**|✅ Yes (`list.get(index)`)|❌ No|❌ No|❌ No (but can access by key)|
|**Common Implementations**|`ArrayList`, `LinkedList`|`HashSet`, `LinkedHashSet`, `TreeSet`|`LinkedList`, `PriorityQueue`, `ArrayDeque`|`HashMap`, `LinkedHashMap`, `TreeMap`|
|**Use case**|When order and duplicates matter|When uniqueness is important|FIFO/LIFO structures|Key-value pairs|

1. **List** 
	-  **properties**
		1. **use kab karna hai** - jab ak ke baad element chahiye
		2. element repeat ho sakte hai
	-  **implementation**
		1. Array List
		2. LinkedList
		3. Stack
	- **example** - `[1, 2, 3, 4]`
2. **Set**
	- **properties**:
		1. unique, **no repeat elements**
		2. uses Hashing (inbuild functions calculate hash code and and decides position of element).
	- **Implementation**: 
		1. HashSet
		2. Linked HashSet
		3. Tree Set
	- **Example:** `(2, 1, 3)`
3. **Queue**
	- **properties:**
		1. Order is based on insertion
		2. **FIFO**
	- **implementation:**
		1. Array Queue
		2. Linked List
		3. Priority Queue (max heap, min heap)

- **Map**
	- **properties:**
		1. **unique keys, value may repeat**
	- **implementation**:
		1. HashMap
		2. tree map - **stores in sorted order using binary trees**

---

### ✅ Summary

- **List** → Ordered, allows duplicates
    
- **Set** → Unordered (unless using `LinkedHashSet`), unique elements
    
- **Queue** → Used for processing items in order (FIFO, LIFO)
    
- **Map** → Key-value pairs, keys must be unique
    

---
