---
tags:
  - dsa
  - array
  - two-pointer
status: 🟩
---

2026-01-15        13:46

---
# What is Four Sum?

```cpp
bool find4Numbers(vector<int>& A, int X) {
    int n = A.size();
    if (n < 4) return false;

    sort(A.begin(), A.end());

    // Fix first element
    for (int i = 0; i < n - 3; i++) {

        // Fix second element
        for (int j = i + 1; j < n - 2; j++) {

            int start = j + 1;
            int end = n - 1;
            int target = X - A[i] - A[j];

            // Two pointer for remaining 2 elements
            while (start < end) {
                int sum = A[start] + A[end];

                if (sum == target) {
                    return true;
                } 
                else if (sum < target) {
                    start++;
                } 
                else {
                    end--;
                }
            }
        }
    }

    return false;
}
```

![[four-sum]]


| Two Pointer |     |
| ----------- | --- |
| O(n³)       |     |


---
