---
tags:
  - index
---

## Day 1

### 1. Introduction to DSA

1. **Data** - Set of information
	- Peene ke liye pani manga tha, balti me le aye
	- Data sahi tha lekin structure galat hai

2. **Algorithm** - approach
	1. Set of information to perform a specific task
	2. chai ke ingredients
		1. water
		2. tea
		3. sugar
		4. elaichi
		5. milk
	3. Chai banane ke different recepies - algorithm

3. **Time complexity**
	1. Time taken to perform a task

### 2. Java basics

- [[basic java code skeleton]]
### 3. Collections and frameworks in Java

- [[What are collections in java]]
- [[what is interface in java]]
- [[interface vs class in java]]

### 4. Difference b/w List, Set, Queue, Map

- [[difference between list, set, queue and map]]
### 5. Implementation of interfaces

- [[iterators in java]]

1. [[List in java]]
	1. [[ArrayList in java]]
	2. [[LinkedList in java]]
		1. [[ArrayList vs LinkedList]]
		2. [[how dynamic array works]]
		3. [[what is autoboxing and unboxing in java]]
	3. [[Stack in java]]
2. [[Queue in java]]
	- Difference b/w `poll()` vs `peek()` vs `remove()`
	- Difference b/w `offer()` vs `add()`
	1. [[PriorityQueue in java]]
		- **min-heap**
			- top node is minimum
			- complete binary tree (all nodes are in same level)
			-             5
			-          /     \
			-      10         20
			-     /   \        /    \
			- 15   25     35    40
		- **max-heap**
			-            40
			-          /     \
			-      35         30
			-     /   \        /    \
			- 25   20     15    10
	2. [[ArrayDeque in java]]
3. [[Set in java]]
	1. [[HashSet in java]]
		- Doesn't maintains order
	2. LinkedHashSet
		- Maintains Order
	3. TreeSet
		- Keeps elements sorted using binary search Tree
	4. [[HashSet vs LinkedHashSet vs TreeSet]]
4. Map in java
	1. [[HashMap in java]]
	2. [[TreeMap in java]]


- tostring()
- equals()
- comparable()
## Day 2

- Stack
- Queue
- PriorityQueue
- Array Deque (Double ended queue)
	- Insertion and deletion available from both end
- Set
	- equals()
	- hashcode()

## Day 3

- **HashMap inner working**
	- **Equals function** =>` equals()`
		- Used to compare value of objects
	- **Hashcode function**
		- used in HashSet HashMap
		- returns key where to store object
		- collision 
			- hashcode is same for two objects
			- uses `equals()` to check if elements are same
				- true - replace old with new or ignore new
				- false - stores on same hash code index after first object in form of LinkedList
	- **tostring function** => `toString()`
		- converts to string, 
		- used to print Objects, else `print()` will log address or hashcode.
		- Collections like `List`, `ArrayList` already have built in `toString()` function.
	- HashSet and HashMap working
- **Comparator vs Comparable:**

## **Day 4**

1. **Time Complexity**
	- Types of equations:
		1. **Linear** => $y = mx + c => ax + by + c = 0$
		2. **Quadratic** => $y = ax^2 + bx + c$

## day 5

## day 6

1. string builder vs stringbuffer
2. Arrays




## Arrays

