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