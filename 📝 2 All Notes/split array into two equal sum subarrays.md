---
tags:
  - array
  - dsa
  - two-pointer
status:
---

2026-01-15        21:54

---
# What is Title?

## Solution

### Solution 1:

- calculate half of sum of array.
- loop through array size-1 (because we want sub arrays)
	- if sum of elements equal to half sum of total array
		- return true

![[split-array-into-two-equal-sum-subarrays | 1000]]

```cpp
class Solution {
public:
	bool canSplit(vector<int>& nums) {
		//code here
		int n = nums.size();
		float total_sum = 0, half_sum = 0;
		for(int i=0; i<n; i++){
			total_sum+=nums[i];
		}
		half_sum = total_sum/2;
		float local_sum=0;
		for(int i=0; i<n-1; i++){
			local_sum+=nums[i];
			if(local_sum == half_sum)
				return 1;
		}
		return 0;
	}
};
```

---
