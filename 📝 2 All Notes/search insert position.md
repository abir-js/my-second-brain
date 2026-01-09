---
tags:
  - dsa
  - java
  - cpp
  - binary-search
status: 🟩
---

2025-09-28        13:04

---
# Search Insert position?

```cpp
class Solution { 
	public: int searchInsert(vector<int>& nums, int target) { 
		int n = nums.size();
		int index = n;    // if target is grater than last element of array
		int start = 0, end = n-1;
		while(start <= end) {
			int mid = start + (end-start)/2;
			if (nums[mid] == target)
				 return mid; 
			else if(nums[mid] < target)
				start = mid + 1;
			else {
				index = mid;    // if mid is grater than target, then we can assign mid value to index
				end = mid - 1;
			}
		 }
		 return index;
	 }
 };
```

![[search-insert-position | 700]]

---
