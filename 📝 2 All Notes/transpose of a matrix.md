---
tags:
  - 2d-array
  - dsa
status: 🟩
---

2026-01-26        18:52

---
# What is Title?

![[transpose-of-a-matrix | 1000]]


```cpp
vector<vector<int>> transpose(vector<vector<int>>& mat) {
    for(int i=0; i<mat.size(); i++){
		for(int j=i+1; j<mat[0].size(); j++){
			if(i == j){
				continue;
			} else {
				swap(mat[i][j], mat[j][i]);
			}
		}
	}
	return mat;
}
```

---
