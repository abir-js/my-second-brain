---
tags:
  - java
status: 🟩
---

2025-08-03        10:27

---
Here’s a **visual comparison** of `HashSet`, `LinkedHashSet`, and `TreeSet` in Java:

---

### 🧾 **Set Types Comparison Table**

|Feature|`HashSet`|`LinkedHashSet`|`TreeSet`|
|---|---|---|---|
|**Order Maintained**|❌ No|✅ Yes (insertion order)|✅ Yes (sorted order)|
|**Duplicates**|❌ Not allowed|❌ Not allowed|❌ Not allowed|
|**Null Elements**|✅ One null allowed|✅ One null allowed|❌ Not allowed|
|**Performance**|Fast (O(1))|Slightly slower than `HashSet`|Slower (O(log n))|
|**Internal Structure**|Hash table|Hash table + Linked List|Red-Black Tree (self-balancing BST)|
|**Use Case**|Quick lookup, ignore order|Maintain order of elements inserted|Automatically sorted elements|
|**Implements**|`Set`|`Set`|`NavigableSet`, `SortedSet`, `Set`|

---

### 🧪 Example Outputs

```java
Set<String> hashSet = new HashSet<>();
Set<String> linkedHashSet = new LinkedHashSet<>();
Set<String> treeSet = new TreeSet<>();

List<String> items = List.of("Banana", "Apple", "Mango", "Apple");

for (String item : items) {
    hashSet.add(item);
    linkedHashSet.add(item);
    treeSet.add(item);
}

System.out.println("HashSet: " + hashSet);
System.out.println("LinkedHashSet: " + linkedHashSet);
System.out.println("TreeSet: " + treeSet);
```

### 🧾 Possible Output:

```
HashSet:       [Mango, Apple, Banana]     // Unordered
LinkedHashSet: [Banana, Apple, Mango]     // Insertion order
TreeSet:       [Apple, Banana, Mango]     // Sorted order
```

---

### 🔚 Summary:

- Use **`HashSet`** when you just need uniqueness and don’t care about order.
    
- Use **`LinkedHashSet`** when you want to **preserve insertion order**.
    
- Use **`TreeSet`** when you need a **sorted set**.
    

---
