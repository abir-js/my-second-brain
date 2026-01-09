---
tags:
  - sorting
  - java
  - dsa
  - cpp
status:
---

2025-09-04        20:58

---
# What is Insertion Sort?

## Inspiration
Cards game
## Idea
Pick an element (from unsorted part) and place in the right pos in sorted part.

## code

```cpp
class Solution {
public:
	vector<int> insertionSort(vector<int>& arr) {
		// Write your code here
		int n = arr.size();
		
		for(int i=1; i<n; i++){
			for(int j=i; j>0; j--){
				if(arr[j-1] > arr[j]){
					swap(arr[j-1], arr[j]);
				} else break;
			}
		}
		return arr;
	}
};
```

## Visualisation

![[insertion-sort]]

## Code

```java
public static void insertionSort(int arr[]) {
	for (int i = 1; i < arr.length; i++) {
		for (int j = i; j > 0; j--) {
			if (arr[j] < arr[j - 1])
				swap(arr, j, j - 1);
		}
	}
	printArray(arr);
}
```

## Insertion Sort Reverse

![[insertion-sort-reverse]]

```java
public static void insertionSortReverse(int arr[]) {
	int n = arr.length;
	for (int i = n - 2; i >= 0; i--)
		for (int j = i; j < n - 1; j++)
			if (arr[j] > arr[j + 1])
				swap(arr, j, j + 1);
			else
				break;
	printArray(arr);
}
```

## Time complexity

### Best case

`arr = [1, 2, 3, 4, 5]`

| Best Case | Worst Case |
| --------- | ---------- |
| O(n)      | O(n²)      |


---
