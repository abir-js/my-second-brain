---
tags:
  - binary-search
  - dsa
status: 🟩
---

2026-01-11        11:49

---
# Peak element in mountain array?

## Solution 1 : Linear Search

- linear search and find largest
	- but it will give TLE

## Binary Search

```cpp
class Solution {
public:
	int peakIndexInMountainArray(vector<int>& arr) {
		int n = arr.size();
		int start = 0, end = n-1;
		while(start <= end){
			int mid = start + (end-start)/2;
			if(arr[mid] > arr[mid-1] && arr[mid] > arr[mid+1]){
				return mid;
			}
			else if(arr[mid] > arr[mid-1]){
				start = mid + 1;
			}
			else {
				end = mid - 1;
			}
		}
		return -1;
	}
};
```




![[peak-element-in-mountain-array | 1000]]

---
