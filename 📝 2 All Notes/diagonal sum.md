---
tags:
  - array
  - java
  - dsa
status: 🟩
---

2025-09-25        09:13

---
# Diagonal Sum?

![[diagonal-sum | 700]]

```
PD = matrix[0][0] + matrix[1][1] + matrix[2][2] + ...
	= sum += matrix[i][i]
	
SD = matrix[0][3] + matrix[1][2] + matrix[2][1] + ...
	3 = matrix.length - 1
	= if(i+j = matrix.length - 1)
		sum += matrix[i][j]
		
Optimized
SD = if(i)
```

```java
public static void printDiagonal(int matrix[][]) {
	int sum = 0;
	for (int i = 0; i < matrix.length; i++) {
		for (int j = 0; j < matrix[0].length; j++) {
			if (i == j)
				sum += matrix[i][j];
			else if (i + j == matrix.length - 1)
				sum += matrix[i][j];
		}
	}
}
```

### Optimized

```java
public static void printDiagonal(int matrix[][]) {
	int sum = 0;
	for (int i = 0; i < matrix.length; i++) {
		// PD
		sum += matrix[i][i];
		// SD
		if (i != matrix.length - i - 1)
			sum += matrix[i][matrix.length - i - 1];
	}
	System.out.println(sum);
}
```

---
