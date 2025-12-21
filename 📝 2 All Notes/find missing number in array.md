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
# Find missing number in array?

## Step 1:

compare n natural numbers with array, if missing return

```cpp
for(int i = 1; i<arr.size+1; i++){  // loops through 1 to n
	bool found = false;
	for(int j = 0; j< size; j++) {  // 
		if(i == arr[j]) {
			found = true;
		}
	}
	if(found == false) {
		return i;
	}
}
```

## Step 2:

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

## Step 3

take XOR of all elements, XOR cancels same element.

```cpp
class Solution {
  public:
    int missingNum(vector<int>& arr) {
        // code here
        int size = arr.size();
        int ans = 0;
        
        // xor all array elements
        for(int i=0; i<size; i++){
            ans = ans^arr[i];
        }
        
        // xor all natural numbers
        for(int i=1; i<=size+1; i++){
            ans = ans^i;
        }
        
        return ans;
    }
};
```

```cpp
class Solution {
  public:
    int missingNum(vector<int>& arr) {
        // code here
        int size = arr.size();
        int ans = 0;
        
        // xor all array elements
        for(int i=0; i<size; i++){
            ans = ans^arr[i]; // for xor of all array element
            ans = ans^(i+1); // for xor of 1 to n-1 element
        }
        ans = ans ^ (size+1);// for last element of n natural number
        
        return ans;
    }
};
```




---
