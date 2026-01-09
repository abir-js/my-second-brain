---
tags:
  - dsa
  - array
  - binary-search
  - cpp
status: 🟩
---

2026-01-08        17:46

---
# Sqrt(x)?

- binary search
- if (mid * mid < target)
	- ans = mid
	- start = mid + 1

```cpp
int mySqrt(int x) {
    // Your code here
	if(x==0) return 0;
	int start = 1, end = x;
	int ans;
	while (start <= end) {
		int mid = start + (end-start)/2;

		if(mid == x/mid)
			return mid;
		else if(mid < x/mid){
			ans = mid;
			start = mid + 1;
		}
		else 
			end = mid - 1;
	}
	return ans;
}
```

![[Excalidraw/Sqrt(x)|Sqrt(x) | 700]]

---
