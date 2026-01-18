---
tags:
  - array
  - dsa
  - two-pointer
status: 🟩
---

2026-01-15        15:16

---
# Product Pair?

- Given an array **`arr[]`** of positive integers and a number **target**, determine if there exists a pair of elements in arr whose product equals **target** . Return **`true`** if such a pair exists, otherwise return **`false`**.

- Example 1:
	- Input: arr = [-10, 20, 9, -40], target = 30
	- Output: false
	- Explanation:
	- No pair exists with product 30.

- Example 2:
	- Input: arr = [10, 20, 9, 40], target = 400
	- Output: true
	- Explanation:
	- As 10 * 40 = 400, the answer is true.

-  Constraints:
	- 1 ≤ arr.length ≤ 10^5
	- -10^8 ≤ arr[i] ≤ 10^8
	- -10^18 ≤ target ≤ 10^18

## Solutions

### 1. Brute force

### 2. Binary search

1. sort array
2. loop through each element and apply binary search

- Time complexity
	- O(n logn)

### 3. 

1. sort the array
2. mid = last negative number
3. if target is positive.
	1. both numbers will be positive
		1. apply two pointer
	2. both numbers will be negative
		1. apply two pointer
4. if target is negative
	1. start = 0, end = mid + 1
	2. to increase, move start
	3. to decrease move end

![[product-pair | 1000]]

```cpp

```

---
