---
tags: 
status:
---

2025-09-25        10:36

---
# Search In sorted Matrix?

### 1. Brute force

### 2. Binary Search in each row or column

### 3. Stare case search

![[stare-case-search]]

```java
class Solution {
	public boolean searchMatrix(int[][] matrix, int target) {
		int row = 0, col = matrix[0].length - 1;
		while (row < matrix.length && col >= 0) {
			if (matrix[row][col] == target) {
				return true;
			} else if (matrix[row][col] < target) {
				row++;
			} else {
				col--;
			}
		}
		return false;
	}
}
```


### Time complexity

#### O(n + m)

---
