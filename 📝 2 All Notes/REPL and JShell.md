---
tags:
  - java
status: 🟩
---

2026-01-07        17:34

---
## JShell in Java (Simply Explained)

![Image](https://journaldev.nyc3.cdn.digitaloceanspaces.com/2015/11/java-repl-example.png)

![Image](https://i.imgur.com/M4jYjGf.png)

![Image](https://media.geeksforgeeks.org/wp-content/uploads/jShell2.png)

### What is **JShell**?

**JShell** is Java’s **interactive shell (REPL)** — _Read → Evaluate → Print → Loop_.  
It lets you **write and run Java code instantly**, without creating a class or a `main()` method.

Think of it as:

> “Try Java code line-by-line and see results immediately.”

---

### Why JShell was introduced?

Before JShell:

- You had to write a full program
    
- Compile it
    
- Run it  
    Even for a **single line test**
    

JShell solves this by allowing **instant experimentation**.

---

### How to start JShell

Open terminal / command prompt and type:

```bash
jshell
```

You’ll see:

```text
|  Welcome to JShell -- Version XX
jshell>
```

---

### Example: Using JShell

```java
jshell> int a = 10;
a ==> 10

jshell> int b = 20;
b ==> 20

jshell> a + b
$1 ==> 30
```

👉 No class  
👉 No `main()`  
👉 Immediate output

---

### Defining methods in JShell

```java
jshell> int add(int x, int y) {
   ...> return x + y;
   ...> }
|  created method add(int,int)

jshell> add(5, 7)
$2 ==> 12
```

---

### Variables & snippets

JShell stores code as **snippets**:

```java
jshell> int x = 5;
jshell> x = 9;
```

Check snippets:

```java
jshell> /vars
jshell> /methods
```

---

### Useful JShell commands

|Command|Purpose|
|---|---|
|`/help`|Show help|
|`/list`|Show entered code|
|`/vars`|Show variables|
|`/methods`|Show methods|
|`/reset`|Clear everything|
|`/exit`|Exit JShell|

---

### When should you use JShell?

✅ Learning Java  
✅ Testing logic  
✅ Trying APIs  
✅ Debugging expressions  
❌ Not for large applications

---

### JShell vs Normal Java Program

|Feature|JShell|Normal Java|
|---|---|---|
|Needs `main()`|❌|✅|
|Compilation|Automatic|Manual|
|Best for|Practice & testing|Real applications|

---

### One-line summary

> **JShell is to Java what a calculator is to math — quick, interactive, and perfect for learning.**


---
