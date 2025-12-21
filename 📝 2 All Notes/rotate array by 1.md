---
tags:
  - dsa
  - cpp
status: 🟩
---

2025-12-18        21:19

---
# Rotate array by 1?

### Right Rotation Algorithm

1. **Backup:** Save the last element: `temp = arr[n-1]`.
2. **Shift:** For `i` from `n-2` down to `0`:
    - Set `arr[i+1] = arr[i]`.
3. **Insert:** Set `arr[0] = temp`.

```cpp
class Solution {
  public:
    void rotate(vector<int> &arr) {
        // code here
        int n = arr.size();
        int last = arr[size-1];
        
        for(int i=n-2; i>=0; i--){
            arr[i+1] = arr[i];
        }
        arr[0] = last;
    }
};
```

---
