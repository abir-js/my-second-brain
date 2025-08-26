---
tags:
  - java
  - dsa
status: 🟩
---

2025-07-31        11:35

---
# What is Array?

In Java, an **array** is a container object that holds a fixed number of values of a **single type**. The length of an array is established when the array is created. After creation, its length is fixed.

List of elements of same type in contiguous memory location.

---

![[array-visualixation-in-memory]]

### 🔹 Syntax for Declaring an Array

```java
// Declaration
int[] numbers;    // preferred
// or
int numbers[];    // allowed
```

### 🔹 Creating an Array

```java
numbers = new int[5];  // creates an array of 5 integers
```

You can also declare and create at once:

```java
int[] numbers = new int[5];
// 0,0,0,0,0
```

### 🔹 Initializing an Array (Static Initialization)

```java
int[] numbers = {10, 20, 30, 40, 50};
```

---

### 🔹 Accessing Elements

```java
System.out.println(numbers[0]);  // prints the first element
numbers[1] = 25;                 // updates the second element
```

---

### 🔹 Iterating an Array

```java
for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}

// OR enhanced for-loop
for (int num : numbers) {
    System.out.println(num);
}
```

---

### 🔹 Example Program

```java
public class ArrayExample {
    public static void main(String[] args) {
        int[] numbers = {5, 10, 15, 20};

        System.out.println("Array elements:");
        for (int i = 0; i < numbers.length; i++) {
            System.out.println("Element at index " + i + ": " + numbers[i]);
        }
    }
}
```

---

### 🔹 Key Points

- Index starts at **0**
    
- Accessing out-of-bound index causes **`ArrayIndexOutOfBoundsException`**
    
- Arrays can hold **primitive** or **object** references
    
- Use `.length` (no `()` like methods) to get array size
    

---