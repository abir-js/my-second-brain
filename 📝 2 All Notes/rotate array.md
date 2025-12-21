---
tags:
  - dsa
  - cpp
  - array
status: 🟩
---

2025-12-20        01:47

---
# Rotate array?

## Question

arr = [1, 2, 3, 4, 5, 6, 7], k = 3
ans = [4, 5, 6, 7, 1, 2, 3]

## Solution 1

Rotate array by 1 K times

```cpp
class Solution {
public:
	void rotate(vector<int>& nums, int k) {
		k = k % nums.size();
		while (k>0) {
			int n = nums.size();
			int last = nums[n-1];
			  
			for(int i=n-2; i>=0; i--){
			nums[i+1] = nums[i];
			}
			nums[0] = last;
			k--;
		}
	}
};
```

## Solution 2

- take extra temp array
- add element based on formula (idx + k) % size

![[rotate-array-by-k]]


## Solution 3

- reverse array
- reverse first k values
- reverse rest

![[rotate-array-by-k-reverse]]

```cpp
class Solution {
public:
	void rotate(vector<int>& nums, int k) {
		int n = nums.size();
		int i = 0, j = n - 1;
		k = k % n;
		
		// Reverse Whole array
		while (i < j) {
			int temp = nums[j];
			nums[j] = nums[i];
			nums[i] = temp;
			i++;
			j--;
		}
		
		// Reverse first K element
		i = 0, j = k - 1;
		 
		while (i < j) {
			int temp = nums[j];
			nums[j] = nums[i];
			nums[i] = temp;
			i++;
			j--;
		}
		 
		// Reverse rest element
		i = k, j = n - 1;
		 
		while (i < j) {
			int temp = nums[j];
			nums[j] = nums[i];
			nums[i] = temp;
			i++;
			j--;
		}
	}
};
```

---

## Related

[[rotate array by 1]]