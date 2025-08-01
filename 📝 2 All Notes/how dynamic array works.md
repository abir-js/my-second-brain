---
tags:
  - dsa
  - java
status: 🟩
---

2025-08-02        01:37

---
## 🔧 What is a Dynamic Array?

A **dynamic array** is an array that **resizes itself automatically** when it runs out of space — unlike normal arrays with fixed size.

In Java, `ArrayList` is a perfect example of a dynamic array.

---

## ⚙️ How it Works Internally

Let’s say we use:

```java
ArrayList<Integer> list = new ArrayList<>();
```

### 1. **Initial Capacity**

- Internally, it starts with a default capacity (usually 10).
    
- It has an **internal array** like: `Object[] elementData = new Object[10];`
    

### 2. **Adding Elements**

- When you do `list.add(1)`, the value is placed into the internal array.
    
- Index increases by 1 for the next value.
    

### 3. **When Full**

- Once the internal array is full, it creates a **new array with larger size** (typically `newCapacity = oldCapacity * 1.5` or `2x`).
    
- **All elements are copied** from the old array to the new array.
    

### 4. **Old Array is Discarded**

- The old array is garbage collected.
    
- The `ArrayList` now uses the new, bigger array.
    

---

### 🧠 Example

Say we have:

```java
ArrayList<Integer> list = new ArrayList<>();
```

Let’s say internally it has:

```java
elementData = new Object[4]; // (for simplicity)
```

You add 4 elements:

```java
list.add(10);
list.add(20);
list.add(30);
list.add(40); // still fits
```

Now if you do:

```java
list.add(50); // array is full!
```

It does:

1. Create a new array: `new Object[6]` (or `8`, depends on growth strategy).
    
2. Copy elements from old to new.
    
3. Add `50` to the new array.
    
4. Replace `elementData` with the new array.
    

---

### 📊 Time Complexity

|Operation|Time Complexity|
|---|---|
|Access by index|O(1)|
|Add (amortized)|O(1)|
|Resize (when full)|O(n)|

But because resizing is rare, overall it feels like **O(1)** when adding.

---

### ✅ Key Advantages

- **Automatic resizing**
    
- **Fast access** by index
    
- Easy to use and abstracted
    

---
