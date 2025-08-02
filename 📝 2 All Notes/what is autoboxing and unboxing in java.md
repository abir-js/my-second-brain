---
tags:
  - java
status: 🟩
---

2025-08-02        10:20

---
### 🧠 **Autoboxing and Unboxing in Java**

Java has **primitive types** (like `int`, `double`, `char`) and **wrapper classes** (like `Integer`, `Double`, `Character`).  
Autoboxing and unboxing help convert between these automatically.

---

### ✅ **Autoboxing**:

_Converting a primitive → to its wrapper class._

```java
int x = 5;
Integer y = x; // autoboxing
```

Behind the scenes:

```java
Integer y = Integer.valueOf(x);
```

---

### ✅ **Unboxing**:

_Converting a wrapper class → to its primitive type._

```java
Integer a = 10;
int b = a; // unboxing
```

Behind the scenes:

```java
int b = a.intValue();
```

---

### 💡 Why it's useful:

Before Java 5 (no autoboxing), you'd write:

```java
List<Integer> list = new ArrayList<>();
list.add(Integer.valueOf(10));
int x = list.get(0).intValue();
```

After Java 5 (with autoboxing/unboxing):

```java
List<Integer> list = new ArrayList<>();
list.add(10); // autoboxing
int x = list.get(0); // unboxing
```

---

### 📌 Common Use Cases:

|Situation|Example|
|---|---|
|Add primitive to a `List<Integer>`|`list.add(5);` (autoboxed to `Integer`)|
|Get from list and use in math|`int x = list.get(0);` (unboxed)|
|Compare|`Integer a = 10; int b = 10; if (a == b)` (unboxing happens)|

---

### ⚠️ Caution: Use `.equals()` with wrappers

Because:

```java
Integer a = 128;
Integer b = 128;
System.out.println(a == b); // false, different objects


Integer c = 100;
Integer d = 100;
System.out.println(c == d); // true, due to integer caching
```

### ⚙️ What's happening:

#### ✅ 1. `Integer a = 128; Integer b = 128;`

- Both `a` and `b` are **wrapper objects** (not primitives).
    
- Java **does not cache** Integer objects beyond the range `-128 to 127`.
    
- So here, **two separate `Integer` objects** are created for 128.
    
- Hence:
    
    ```java
    a == b  // false → because different memory locations
    ```
    

---

#### ✅ 2. `Integer c = 100; Integer d = 100;`

- Java **does cache** integers from `-128` to `127`.
    
- This is an optimization called **Integer Caching**.
    
- Both `c` and `d` point to the **same cached object** for 100.
    
- Hence:
    
    ```java
    c == d  // true → both refer to the same object
    ```
    

---

### 🔥 Summary:

|Code|Result|Reason|
|---|---|---|
|`Integer a = 128;`||New object|
|`Integer b = 128;`||Another new object|
|`a == b`|false|Different objects|
|`Integer c = 100;`||Uses cached object|
|`Integer d = 100;`||Uses same cached object|
|`c == d`|true|Same memory reference|

---

### ✅ Best Practice:

Always use `.equals()` to compare object values, not `==`, unless you're sure you're comparing **memory references**.

```java
System.out.println(a.equals(b)); // true
System.out.println(c.equals(d)); // true
```

Want to see how to disable or customize the caching range?

Instead use:

```java
System.out.println(a.equals(b)); // true
```

---
