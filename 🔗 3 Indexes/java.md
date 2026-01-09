---
tags:
  - index
---
---

## Java
### 0. Java Basics

1. [[REPL and JShell]]

2.  [[What is Java]]
3. [[What is JDK]]
4. [[What is JRE]]
5. [[What is JVM]]
6. [[JDK JVM JRE summery]]
7. [[How a JAVA program runs]]
8. [[basic java code skeleton]]
### 1. Datatypes

1. [[datatypes in java]]
2. [[why java is not pure object oriented language]]
3. [[UNICODE and ASCII value]]
4. [[widening or implicit conversion in java]]
5. [[narrowing or explicit conversion in java]]
6. [[String in java]]

### 2. Arithmetic and Bitwise Operation 

1. [[arithmetic and bitwise operation in java]]

### 3. If-else, loops and flow control 

1. [[if-else, loops and flow control in java]]
### 4. Arrays in JAVA

- [[array in java]]









## DSA in Java - Apna College
### 1. Flowcharts and pseudocode

### 2. Variables and datatypes

1. [[first java code]]
2. [[output in java]]
3. [[variables in java]]
4. [[datatypes in java]]
5. [[input in java]]
6. [[type conversion in java]]
7. [[type casting in java]]
8. [[type promotion in java]]

### 13. Arrays

1. [[array in java]]
2. [[contiguous memory allocation in array]]
3. [[why zero based indexing in array]]
4. [[32 bit vs 64 bit processor]]
5. [[creating an array in java]]
6. [[passing arrays as arguments]]
7. [[linear search]]
8. [[binary search]]
9. [[reverse array]]
10. [[print continuous subarrays]]
#### Questions Coder Army

1. [[search an element in an array]]
2. [[reverse array]]
3. [[find second max in array]]
4. [[find missing number in array]]
5. [[rotate array by 1]]

### 14. Arrays (Part II)
1. [[max subarray sum]]
2. [[max subarray sum using kadane's algo]]
3. [[trapping rainwater problem]]
4. [[best time to buy and sell stocks]]
5. [[217. contains duplicates]]

#### Cohort
1. [[66. plus one]]
2. [[best time to buy and sell stocks]]

### 15. Sorting

1. [[bubble sort]]
2. [[selection sort]]
3. [[insertion sort]]
4. [[inbuilt sort]]
5. [[counting sort]]

### 16. 2D Array

- [[2d arrays in memory]]
#### Problems
- [[spiral matrix]]
- [[diagonal sum]]
- [[search in sorted matrix]]

Cohort
- [[island parameter]]
- [[majority element]]
- [[move zeros]]
- [[relative ranks]]
- [[distribute candies]]
- [[baseball games]]

### Binary Search

- [[binary search]]

### Linked List

- [[linked list in java]]

#### Problems
- [[find first and last position of element in sorted array]]
- [[search insert position]]

### 23. Time and space complexity

1. [[Time and Space Complexity]]

### 28. Stack



## DSA in JAVA Cohort

### Day 1

#### 1. Introduction to DSA

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

#### 2. Java basics

- [[basic java code skeleton]]
#### 3. Collections and frameworks in Java

- [[What are collections in java]]
- [[what is interface in java]]
- [[interface vs class in java]]

#### 4. Difference b/w List, Set, Queue, Map

- [[difference between list, set, queue and map]]
#### 5. Implementation of interfaces

- [[iterators in java]]

1. [[List in java]]
	1. [[ArrayList in java]]
	2. [[LinkedList interface in java]]
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
### Day 2

- Stack
- Queue
- PriorityQueue
- Array Deque (Double ended queue)
	- Insertion and deletion available from both end
- Set
	- equals()
	- hashcode()

### Day 3

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

### Day 4

1. **Time Complexity**
	- Types of equations:
		1. **Linear** => $y = mx + c => ax + by + c = 0$
		2. **Quadratic** => $y = ax^2 + bx + c$

### day 5

### day 6 - Arrays

#### Problems: 

- **powerOfTwo**

```java
class Solution {
	public boolean isPowerOfTwo(double n) {
		if(n == 1) return true;
		else if(n < 1) return false;
		else return isPowerOfTwo(n/2.0);
	}
}
```

- **powerOfFour**
- **3304. Find Kth Character in String Game**

> Problem: Word starts from "a"
> +1 and add, "a" -> "ab" -> "abbc"
> return kth character

```java
StringBuilder word = new StringBuilder("a");

void getWord(int k){
	if(k <= 1) {
		return;
	}
	else {
		StringBuilder temp = new StringBuilder();
		int originalLength = word.length();

		int i = 0;
		while(i < originalLength){
			// Check old string's first character
			// increase by 1 
			// add it in temp
			if (word.charAt(i) == "z") 
				temp.append("a");
			else
				temp.append((char)word.charAt(i) + 1);
			
			i++; k--;
		}
		word.append(temp);
		getWord(k);
	}
}
```

1. string builder vs stringbuffer

#### Arrays

[[arrays in dsa]]


###  day 7 - LinkedList

[[linkedlist in java]]

### day 8 - LinkedList part 2

### day 9 - stack and queue

- priority queue

### day 10 - trees



## Arrays



