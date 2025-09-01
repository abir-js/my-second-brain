---
tags:
  - array
  - java
  - cpp
  - dsa
status: 🟩
---

2025-09-01        16:51

---
# What is Title?

## Step:

sum of n natural number - sum of array

[GFG](https://www.geeksforgeeks.org/problems/missing-number-in-array1416/1)


```java
class Solution {
    int missingNum(int arr[]) {
        // The number of elements in the given array + 1
        int n = arr.length + 1;
        
        // --- FIX ---
        // Use 'long' for sum calculations to prevent overflow.
        // Cast 'n' to long to ensure the multiplication is done using 64-bit arithmetic.
        long totalSum = (long)n * (n + 1) / 2;
        
        // Also use 'long' for the array sum for consistency.
        long arraySum = 0;
        for (int num : arr) {
            arraySum += num;
        }
        
        // The difference is the missing number.
        // Cast the final result back to 'int' as the answer is guaranteed to fit.
        return (int)(totalSum - arraySum);
    }
}
```

---
