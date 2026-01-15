---
tags:
  - dsa
  - two-pointer
  - array
status: 🟩
---

2026-01-15        14:30

---
# What is Title?

- You are given a one-dimensional unsorted array **arr** containing **n** integers and an integer **diff** . Find if there exists a pair of elements in the array whose absolute difference is exactly **diff** .

- Return **1** if any such pair exists, else return **0**.

## Example

- Example 1:
	- Input: arr = [-10, 20], diff = 30
	- Output: 1
	- Explanation:
	- Pair (-10, 20) have an absolute difference of 30.

## Two Pointer approach

- Normal one from front and back wont work because for both `i++` and `j--` the difference value will decrease

### Two pointer from front

- start, end = 0 because for single element, it would start from same element and their difference will be 0. 

```cpp
int pairWithGivenDifference(vector<int>& arr, int diff) {	
	// Your code here	
	sort(arr.begin(), arr.end());	
	int n = arr.size();		  	
	int start = 0, end = 0;	
	while(start <= end && end < n){	
		if(arr[end] - arr[start] == diff)	
			return 1;	
		else if(arr[end] - arr[start] < diff)	
			end++;	
		else	
			start++;	
	}	
	return 0;
}
```

---
