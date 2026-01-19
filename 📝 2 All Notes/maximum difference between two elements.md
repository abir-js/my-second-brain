---
tags:
  - prefix-sum
  - array
  - dsa
status: 🟩
---

2026-01-19        16:53

---
# What is Title?

## Solution 

### 1. Brute force

```cpp
int maxDiff(vector<int> &arr) {
    // Your code here
    int n = arr.size();

	int maxDiff, currDiff = -1;

	if(n == 1)
		return -1;

	for(int i=0; i<n-1; i++){
		for(int j=i+1; j<n; j++){
			if(arr[i] < arr[j]){
				currDiff = arr[j] - arr[i];
			}
			if(currDiff > maxDiff)
				maxDiff = currDiff;
		}
	}

	return maxDiff;
}
```

![[maximum-difference-between-two-elements | 1000]]

### 2. Solution 2

- traverse through array and maintain smallest element
- on each iteration calculate `arr[i] - smallest`
- take the largest difference

```cpp
int maxDiff(vector<int> &arr) {
	// Your code here
	int n = arr.size();
	int maxDiff = -1;
	if(n == 1)
		return -1;
	
	int minValue = INT_MAX;
	for(int i=0; i<n; i++){
		if(arr[i] < minValue)
			minValue = arr[i];
		if(minValue == arr[i])
			continue;
		if(arr[i] - minValue > maxDiff)
			maxDiff = arr[i] - minValue;
	}
	return maxDiff;
}
```

---
