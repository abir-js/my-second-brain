---
tags:
  - java
  - dsa
status: 🟩
---

2025-08-23        12:56

---
# What is Linear Search?

```java
  

public class LinearSearch {

	public static int linearSearch(int arr[], int target) {
		for (int i = 1; i < arr.length; i++) {
			if (target == arr[i]) {
				return i;
			}
		}
		return -1;
	}

  

	public static void main(String[] args) {
	
		int numbers[] = { 2, 4, 6, 8, 10, 12, 14, 16 };
		int target = 10;
		// find index of 10
		int index = linearSearch(numbers, target);
		if (index == -1)
			System.out.println("Element is not present in array");
		else
			System.out.println("Elememnt is present at index: " + index);
		}
	
}
```

---
