---
tags:
  - dsa
  - java
status: 🟩
---

2025-09-24        11:37

---
# Majority element?

### 1. Hashing



### 2. Boyer Moore Algorithm

- If same element, increase count
- If different element decrease count
	- if count == 0
		- take current element in result
		- increase count to 1

![[boyer-moore-algo]]

```java
class Solution {
	public int majorityElement(int[] nums) {
		int result = nums[0], count = 1;
		for(int i=1; i<nums.length; i++){
			if(nums[i] == result) count++;
			else {
				count--;
				if(count == 0) {
					result = nums[i];
					count++;
				}
			}
		}
		return result;
	}
}
```

---
