---
tags:
  - 2d-array
  - dsa
status: 🟩
---

2026-01-26        12:23

---
# What is Title?

```cpp
vector<vector<int>> addTwoMatrix(vector<vector<int>>& mat1, vector<vector<int>>& mat2) {
	if(mat1.size() != mat2.size() || mat1[0].size() != mat2[0].size()){
		vector<vector<int>>ans(1, vector<int>(1));
		ans[0][0] = -1;
		return ans;
	}
    vector<vector<int>>ans(mat1.size(), vector<int>(mat1[0].size()));
	for(int i=0; i<mat1.size(); i++){
		for(int j=0; j<mat1[0].size(); j++){
			ans[i][j] = mat1[i][j] + mat2[i][j];
		}
	}

	return ans;
}
```

---
