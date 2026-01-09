---
tags:
  - java
status:
---

2025-07-31        10:30

---
## ✅ 1. **if-else Statements** (Decision Making)

Used to execute code blocks based on a **boolean condition**.

### 🔹 Syntax:

```java
if (condition) {
    // code if condition is true
} else {
    // code if condition is false
}
```

### 🔹 Example:

```java
int age = 18;
if (age >= 18) {
    System.out.println("You are an adult.");
} else {
    System.out.println("You are a minor.");
}
```

### 🧩 Other forms:

- `if`
    
- `if-else`
    
- `if-else if-else`
    
- Nested `if`
    

---

## 🔁 2. **Loops in Java**

Used to execute a block of code **repeatedly**.

### 🔹 a. **for loop**

```java
for (int i = 1; i <= 5; i++) {
    System.out.println("i = " + i);
}
```

➡️ Repeats from i = 1 to 5.

---

### 🔹 b. **while loop**

```java
int i = 1;
while (i <= 5) {
    System.out.println("i = " + i);
    i++;
}
```

➡️ Runs **as long as the condition is true**.

---

### 🔹 c. **do-while loop**

```java
int i = 1;
do {
    System.out.println("i = " + i);
    i++;
} while (i <= 5);
```

➡️ **Always executes once**, even if condition is false.

---

## 🎛 3. **Flow Control Statements**

### 🔸 a. **break** – exits the loop or switch block

```java
for (int i = 1; i <= 10; i++) {
    if (i == 5) break;
    System.out.println(i);
}
```

➡️ Output: 1 2 3 4

---

### 🔸 b. **continue** – skips the current iteration

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3) continue;
    System.out.println(i);
}
```

➡️ Output: 1 2 4 5 (3 is skipped)

---

### 🔸 c. **return** – exits from a method

```java
public static void check(int num) {
    if (num < 0) return;
    System.out.println("Number is: " + num);
}
```

---

## 🧭 4. **Visual Flow Control Diagram**

```
       +------------------------+
       |       Start            |
       +------------------------+
                    |
                    v
            [ if (condition) ]
             /           \
         true             false
         /                  \
[execute true block]   [execute else block]
         \                  /
          \                /
           +--------------+
           |    Continue   |
           +--------------+
```

---

## 🔄 5. **Loop Flow Diagram (for, while)**

```
       +---------------------+
       | Initialization      |
       +---------------------+
                   |
                   v
         +--------------------+
         |  Check Condition   |
         +--------------------+
               /    \
           true      false
            |           |
      +-----------+     |
      | Loop Body |<----+
      +-----------+
            |
       Increment / Update
            |
            v
     (go back to Check Condition)
```

---