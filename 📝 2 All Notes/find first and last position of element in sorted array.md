---
tags: 
status:
---

2025-09-24        12:24

---
# Find first and last occurrence of elements in sorted array ?

## 1. Method 1 (Linear search)

- Start searching linearly from first
	- If matched, put in first
- Search from back
	- if matched, put in last
- If not found, return -1
- Time complexity O(n)

## 2. Method 2 (Binary Search)

```cpp
#include <iostream>
using namespace std;
int main()
{
	int arr[] = {1, 2, 2, 2, 2, 3, 4};
	int n = sizeof(arr) / sizeof(arr[0]);
	int target = 2;
	int first = -1, last = -1;
	
	// For first
	int start = 0, end = n - 1, mid;
	while (start <= end)
	{
		mid = start + (end - start) / 2;
		if (arr[mid] == target)
		{
			first = mid;
			end = mid - 1;
		}
		else if (target > arr[mid])
		{
			start = mid + 1;
		}
		else
		{
			end = mid - 1;
		}
	}
	cout << "Start Position is " << first << endl;
	
	// For Last
	start = 0, end = n - 1;
	while (start <= end)
	{
		mid = start + (end - start) / 2;
		if (arr[mid] == target)
		{
			last = mid;
			start = mid + 1;
		}
		else if (target > arr[mid])
		{
			start = mid + 1;
		}
		else
		{
			end = mid - 1;
		}
	}
	cout << "Last Position is " << last << endl;
	return 0;
}
```


---
