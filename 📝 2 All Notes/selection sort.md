---
tags: 
status:
---

2025-09-04        07:53

---
# What is Selection Sort?

## Idea

- take smallest
- replace with first element
- do same for rest

## Code with explanation

```cpp
// take smallent element from an array and put it ar first
int index = 0;
for(int i=0; i<n; i++){
	if(arr[i] < arr[index])
		index=i;
}
swap(arr[0], arr[index]);
```

```cpp
// repeat same steps for all elements
for(int j=0; i<n; j++){
	int index = j;
	for(int i=j+1; i<n; i++){     // we are using j+1 instead of j bcoz we dont want to compare an element with itself
		if(arr[i] < arr[index])
			index=i;
	}
	swap(arr[j], arr[index])
}
```



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
