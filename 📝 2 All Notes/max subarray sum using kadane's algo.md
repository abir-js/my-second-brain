---
tags:
  - java
  - dsa
  - array
status: 🟩
---

2025-08-26        08:30

---
# What is Kadane's algorithm?

Sum of a big negative number and small positive number is negative, so instead of that, take 0 for prefix sum problem.

`[-2, -3, 4, -1, -2, 1, 5, -3]`

|                 | arr[0] | arr[1] | arr[2] | arr[3] | arr[4] | arr[5] | arr[6] | arr[7] |
| --------------- | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ |
| **Current Sum** | 0      | 0      | 4      | 3      | 1      | 2      | 7      | 4      |
| **Maximum Sum** | 0      | 0      | 4      | 4      | 4      | 4      | 7      | 7      |

```java
public class kadaneAlgo {

	public static void kadanes(int nums[]){
		int currSum = 0;
		int maxSum = Integer.MIN_VALUE;
		for(int i = 0; i< nums.length; i++){
			currSum = currSum + nums[i];
			if(currSum < 0) currSum = 0;
			maxSum = Math.max(maxSum, currSum);
		}
		System.out.println("Maximum Subarray sum is: "+ maxSum);
	}
	public static void main(String[] args) {
		int arr[] = {-2, -3, 4, -1, -2, 1, 5, -3};
		kadanes(arr);
	}
}
```

---
