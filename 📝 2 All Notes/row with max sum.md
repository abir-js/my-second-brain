---
tags: 
status:
---

2026-01-26        18:41

---
# What is Title?

```cpp
int rowWithMaxSum(vector<vector<int>>& mat) {
    // Your code here
    // for empty array
    if(mat.size() == 0 || mat[0].size() == 0){
        return -1;
    }

    int maxSum, idx = 0;

    for(int i=0; i<mat.size(); i++){
        int currSum = 0;
        for(int j=0; j<mat[0].size(); j++){
            currSum += mat[i][j];
        }
        // for negative array, make maxSum = currSum
        if(i>0){
            if(currSum > maxSum){
                maxSum = currSum;
                idx = i;
            }
        } else {
            maxSum = currSum;
            idx = i;
        }
    }
    return idx;
}
```

---
