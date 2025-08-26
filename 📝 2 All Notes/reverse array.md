---
tags:
  - java
  - dsa
status: 🟩
---

2025-08-23        20:22

---
# Reverse an Array


```java
public class reverseArray {
	public static void reverseArr(int arr[]) {

		int i = 0;
	
		int j = arr.length - 1;
		while (i < j) {
			int temp;
			temp = arr[i];
			arr[i] = arr[j];
			arr[j] = temp;
			i++;
			j--;
		}
	}

	public static void main(String[] args) {
		int arr[] = { 1, 2, 3, 4, 5 };
		reverseArr(arr);
		for (int i : arr) {
			System.out.println(i);
		}
	}
}
```

---
