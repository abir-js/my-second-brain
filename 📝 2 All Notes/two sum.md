---
tags:
  - dsa
  - two-pointer
  - binary-search
status: 🟩
---

2026-01-15        12:08

---
# Two Sum II?

- array is sorted.

## Method 1 - Brute force

```cpp
for(i=0; i<n-1; i++)
    for(j=i+1; j<n; j++)
        if(arr[i]+arr[j] == target)      
            return true;
        else
            return false;
```

| Worst | Best |
| ----- | ---- |
| O(n²) | O(1) |

## Method 2 - Binary Search

![[two-sum-using-binary-search| 1000]]

| Worst     |     |
| --------- | --- |
| O(n logn) |     |

---

## Method 3 - two pointer

![[two-sum-using-two-pointer | 1000]]

```cpp
class Solution {
public:
	vector<int> twoSum(vector<int>& nums, int target) {
	//code here
		vector<int> ans;
		int n = nums.size();
		int start = 0, end = n-1;
		while(start <= end){
			if(nums[start]+nums[end] == target){	
				ans.push_back(start+1);		
				ans.push_back(end+1);	
				return ans;	
			} else if(nums[start] + nums[end] < target){	
				start++;	
			} else {	
				end--;	
			}
		}
		return {};
	
	}

};
```