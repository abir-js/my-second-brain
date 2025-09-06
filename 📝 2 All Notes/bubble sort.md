---
tags:
  - sorting
  - array
  - dsa
  - java
status: 🟩
---

2025-09-03        23:51

---
# What is Bubble Sort?

## Idea
Large elements come to the end of array by swapping with adjacent elements.

Array me bade values chote values ko swap kaeke aakhir me chale jate hai

## Example

![[bubble-sort-visualization]]

## Code

```java
public static void bubble_sort(int arr[]) {
	for (int i = n-2; i>=0; i--) {
		for (int j = 0; j <= i j++) {	
			if (arr[j] > arr[j + 1]) {
				int temp = arr[j];
				arr[j] = arr[j + 1];
				arr[j + 1] = temp;
			}
		}
	}
}
```


### Optimum bubble sort

```java
```

## Bubble Sort reverse

![[bubble-sort-reverse]]

### Code

```java
public static void bubbleSortReverse(int arr[]) {
	int n = arr.length;
	for (int i = 0; i < n; i++) {
		for (int j = n - 1; j > i; j--) {
			if (arr[j] < arr[j - 1])
				swap(arr, j, j - 1);
		}
	}
	printArray(arr);
}
```
## Time complexity



---
