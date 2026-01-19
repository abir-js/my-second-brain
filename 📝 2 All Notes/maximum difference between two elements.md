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


---
