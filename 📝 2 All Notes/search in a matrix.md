---
tags:
  - dsa
  - 2d-array
status: 🟩
---

2026-01-26        12:21

---
# What is Title?

```cpp
bool searchMatrix(vector<vector<int>>& matrix, int target) {
    int rows = matrix.size();
	int columns = matrix[0].size();

	for(int i=0; i<rows; i++){
		for(int j=0; j<columns; j++){
			if(matrix[i][j] == target)
				return 1;
		}
	}
	return 0;
}
```

---
