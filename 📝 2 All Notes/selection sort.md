---
tags: 
status:
---

2025-09-04        07:53

---
# What is Selection Sort?

## Idea
pick the smallest (from unsorted), put it at the beginning.

## Visualisation

![[selection-sort]]

## Code

```java
public static void selectionSort(int[] arr) {
	for(int i=0; i<arr.length-1; i++){
		int smallest = i;
		for(int j=i+i; j<n; j++){
			if(arr[j] < arr[smallest]){
				smallest = j;
			}
		}
		swap(arr[i], arr[smallest])
	}
}
```
---
