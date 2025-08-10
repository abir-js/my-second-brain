---
tags:
  - dsa
  - time-space-complexity
status: 🟩
---

2025-08-06        20:39

---

# Time and Space Complexity

## 1. Order Complexity Analysis

- Amount of **Space or Time** taken up by an algorithm/code as function of input size.
- Not the actual time taken.

## 2. What is Time Complexity

>It is the total time taken by an algorithm to run as a function  of the length of the input.


![[Pasted image 20250808180957.png]]

| Properties        | Old Machine | New Machine  |
| ----------------- | ----------- | ------------ |
| **Time Function** | $time = n$  | $time = n/2$ |
| **Type**          | Linear      | Linear       |
> NOTE
> n can be $n/2$, $log(n)$, $n^2$ etc.

---
## Types of Time Complexity

### 1. Worst Case

#### Big(O)

### 3. Average Case

#### Theta (θ)

### 2. Best Case

#### Omega (Ω)

---
## Rules:

1. **Ignore constant terms**

```js
//   1     1    1
for(i=1; i<=n; i++){
//         1
	print("Hello");
}

1    2    3    4  ...  n
4 +  3  + 3  + 3 + ... 3

=> 3n + 1
=> O(n)
```

2. **Take Biggest Power**

$f(n) = 2N^3 + 3N^2 + N$
=> O($n^2$)

---
## Practice Questions

### 1. Linear Search

```cpp
for(i=1; i<=n; i++){
	if(arr[i] == element) {
		cout<<"Found";
		break;
	}
}
```

|                | Best Case                      | Average Case                    | Worst case                    |
| -------------- | ------------------------------ | ------------------------------- | ----------------------------- |
| **Complexity** | Ω(1)                           | θ(n),<br>$n(n+1)/2n = n$        | O(n)                          |
| **Condition**  | Element present at first index | Element present at middle index | Element present at last index |

### 2. Sum of N numbers

$Eq^n => n(n + 1) / 2$

|                | Best Case                      | Average Case                    | Worst case                    |
| -------------- | ------------------------------ | ------------------------------- | ----------------------------- |
| **Complexity** | Ω(1)                           | θ(1),<br>$n(n+1)/2n = n$        | O(1)                          |

### 3. Inner Loops

#### A. Inner loop doesn't depends on outer loop

```cpp
for(i=1; i<=n; i++){
	for(j=1; j<=n; j++){
		cout<<"Done";
	}
}

i = 1      | i = 2              i = n
j = 1 to n | j = 1 to n .....   j = 1 to n
n times    | n times            n times
```

$Eq^n = n + n + n + ... + n = n^2$ 
#### B. Inner Loop depends on outer loop

### 1. $j = i$

```cpp
for(i=1; i<=n; i++){
	for(j=1; j<=i; j++){
		cout<<"Done";
	}
}
```

```sh
i = 1      | i = 2              i = n
j = 1 to 1 | j = 1 to 2 .....   j = 1 to n
1 times    | 2 times            n times

Eq^n = 1 + 2 + 3 +...+ n
= n(n + 1)/2
= (n^2 + n)/2
= O(n^2)
```

$$
Eq^n = 1 + 2 + 3 +...+ n
= n(n + 1)/2
= (n^2 + n)/2
= O(n^2)
$$

### 2. $j = i^2$

```cpp
for(i=1; i<=n; i++){
	for(j=1; j<=i^2; j++){
		cout<<"Done";
	}
}
```

```sh
i = 1      | i = 2              i = n
j = 1 to 1 | j = 1 to 2 .....   j = 1 to n
1 times    | 2 times            n times

Eq^n = 1 + 2 + 3 +...+ n
= n(n + 1)/2
= (n^2 + n)/2
= O(n^2)
```
