---
tags:
  - array
  - dsa
  - java
  - cpp
status: 🟩
---

2025-09-01        16:41

---
# What is Title?

```java
class Solution {
    public int getSecondLargest(int[] arr) {
        // code here
        int max = -1;
        for(int i = 0; i< arr.length; i++){
            if(arr[i] > max) {
                max = arr[i];
            }
        }
        
        int second_max = -1;
        for(int i = 0; i< arr.length; i++){
            if(arr[i] != max && arr[i] > second_max) {
                second_max = arr[i];
            }
        }
        
        return second_max;
        
    }
}
```

---
