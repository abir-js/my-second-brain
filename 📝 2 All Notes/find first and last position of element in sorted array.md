---
tags:
  - dsa
  - cpp
  - array
  - binary-search
status:
---

2025-09-24        12:24

---
# Find first and last occurrence of elements in sorted array ?

## 1. Method 1 (Linear search)

- Start searching linearly from first
	- If matched, put in first
- Search from back
	- if matched, put in last
- If not found, return -1
- Time complexity O(n)

## 2. Method 2 (Binary Search)

```cpp
class Solution {
public:
	vector<int> searchRange(vector<int>& nums, int target) {
		int first = -1;
		int n = nums.size();
		
		// search for first element;
		int start = 0, end = n - 1;
		while (start <= end) {
			int mid = start + (end - start) / 2;
			if (nums[mid] == target) {
				// if found, assume it is the first element and search in first half of array if any other is present
				first = mid;    
				end = mid - 1;
			} else if (nums[mid] > target) {
				end = mid - 1;
			} else {
				start = mid + 1;
			}
		}
		
		// search for last element;
		int last = -1;
		start = 0, end = n - 1;
		while (start <= end) {
			int mid = start + (end - start) / 2;
			if (nums[mid] == target) {
				// if found, assume it is the last element and search in last half of array if any other is present
				last = mid;
				start = mid + 1;
			} else if (nums[mid] > target) {
				end = mid - 1;
			} else {
				start = mid + 1;
			}
		}
		
		vector<int> arr;
		arr.push_back(first);
		arr.push_back(last);
		return arr;
	}
};
```


---
