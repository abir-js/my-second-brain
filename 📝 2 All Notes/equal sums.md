---
tags:
  - prefix-sum
  - dsa
  - array
status: 🟩
---

2026-01-19        11:02

---
# What is Title?

![[equal-sums | 1000]]

```cpp
class Solution {
  public:
    vector<int> EqualSum(vector<int> arr) {
        //Code here
		int n = arr.size();

		int totalSum = 0;
		// take total sum of array
		for(int i=0; i<n; i++){
			totalSum += arr[i];
		}

		int leftSum = 0, rightSum = 0;
		// 0: value of element, 1: 1 based index of element where it will get inserted; 2: left or right subarray
		vector<int> ans(3);
		ans[0] = INT_MAX;

		for(int i=0; i<n-1; i++){
			leftSum += arr[i];
			rightSum = totalSum - leftSum;

			if(abs(leftSum - rightSum) > ans[0])
				continue;
			if(rightSum > leftSum){
				ans[2] = 1;
				ans[0] = rightSum - leftSum;
				ans[1] = i+2;
			} else {
				ans[2] = 2;
				ans[0] = leftSum - rightSum;
				ans[1] = i+2;
			}
		}
		return ans;
    }
};
```

---
