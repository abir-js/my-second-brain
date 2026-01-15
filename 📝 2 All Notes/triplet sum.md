---
tags:
  - dsa
  - two-pointer
  - array
status: 🟩
---

2026-01-15        13:12

---
# What is Title?

- sum of 3 element in unsorted array

## Two pointer approach

1. sort array
2. loop through each element
3. apply two pointer

```cpp
bool hasTripletSum(vector<int> &arr, int target) {
    int n = arr.size();
    if (n < 3) return false;

    sort(arr.begin(), arr.end());    //O(n logn)

    for (int i = 0; i < n - 2; i++) {
        int start = i + 1;
        int end = n - 1;
        int newTarget = target - arr[i];

        while (start < end) {
	        // O(n²)
            int sum = arr[start] + arr[end];

            if (sum == newTarget) {
                return true;
            } 
            else if (sum < newTarget) {
                start++;
            } 
            else {
                end--;
            }
        }
    }
    return false;
}

```


| Two Pointer | Binary Search |
| ----------- | ------------- |
| O(n²)       | O(n² logn)    |


---
