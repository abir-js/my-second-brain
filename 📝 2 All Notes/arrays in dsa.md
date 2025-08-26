---
tags:
  - dsa
status: 🟩
---

2025-08-21        15:05

---

# What is Array?

Array is collection of similar type of data element

```java
int a[];   // Declare
a = new int[10]  // assign

//or
int a = new int[10];

int a[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
```

## Traversing in an array

1. **for-loop**
```java
for(int i=0; i<arr.length; i++){
	System.out.println(a[i]);
}
```

2. **enhanced for-loop**

```java
for(int x : arr){
	System.out.println(x);
}
```

### Questions

- **26. Remove duplicates from sorted array**
	- sorted, non-decreasing array
	- change in original array
	- return number of unique elements in array

![[Pasted image 20250822090518.png]]

```java
int k=1;
for (int i=1; i<arr.length; i++){
	if(arr[i] != arr[i-1]){
		arr[k] = arr[i];
		k++;
	}
}
return k;
```

- **35. Search insert position**

```java
int left = 0, right = arr.length-1;
while(left <= right) {
	int mid = (left + right) / 2;
	if(arr[mid] == target)
		return mid;
	else if(arr[mid] < target)
		left = mid + 1;
	else
		right = mid - 1;
}
return left;
```

- **88. Merge Sorted Arrays**
	1. two arrays with sizes m and n.
	2. merge and sort them in first array which actually has m+n size

![[Pasted image 20250822194112.png]]

- Find bigger b/w i and j, place it in the position ok k
- decrease all of them.

![[Pasted image 20250822232322.png]]

```java

```


- **66. Plus One**


---
