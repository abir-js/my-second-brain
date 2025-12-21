---
tags:
  - java
  - dsa
  - cpp
status: 🟩
---

2025-08-23        20:22

---
# Reverse an Array

## 1. Using half size array

```cpp
class Solution {
  public:
    void reverseArray(vector<int> &arr) {
        // code here
        for(int i=0; i<arr.size()/2; i++){
    		int temp = arr[i];
    		arr[i] = arr[arr.size() - i - 1];
    		arr[arr.size()-i-1] = temp;
	    }
    }
};
```
## 2. Using 2 pointers

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
