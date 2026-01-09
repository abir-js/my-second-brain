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

>It is the total time taken by an algorithm to run as a function of the length of the input.


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

### 2. Best Case

#### Omega (Ω)
### 3. Average Case

#### Theta (θ)

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
=> O($n^3$)

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

$$
Eq^n = n + n + n + ... + n = O(n^2)
$$ 
#### B. Inner Loop depends on outer loop

##### 1. $j = i$

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

##### 2. $j = i^2$

```cpp
for(i=1; i<=n; i++){
	for(j=1; j<=i^2; j++){
		cout<<"Done";
	}
}
```

```sh
i = 1      | i = 2       | i = 3             i = n
j = 1 to 1 | j = 1 to 4  | j = 1 to 9  ....  j = 1 to n^2
1 times    | 4 times     | 9 times           n^2 times

Eq^n = 1 + 2^2 + 3^2 +...+ n^2
= n(n + 1)(2n + 1)/6
= O(n^3)
```

$$
Eq^n = 1 + 2^2 + 3^2 +...+ n^2
= n(n + 1)(2n + 1)/6
= O(n^3)
$$

##### 3. $i = n, j = m$

```cpp
for(i=1; i<=n; i++){
	for(j=1; j<=m; j++){
		cout<<"Done";
	}
}
```

```sh
= O(nm)
```

$$
Eq^n= O(nm)
$$


##### 4. $i <= n, j <= i^2, k<= n/2$

```cpp
for(i=1; i<=n; i++){
	for(j=1; j<=i^2; j++){
		for(k=1; k<=n/2, k++){
			cout("Hello");
		}
	}
}
```

```sh
i = 1        | i = 2        | i = 3             i = n
j = 1 to 1   | j = 1 to 4   | j = 1 to 9  ....  j = 1 to n^2
k = 1 to n/2 | k = 4(n/2)   | k = 9(n/2)        k = n^2(n/2)
n/2 times    | 4(n/2) times | 9(n/2) times      n^2(n/2) times

Eq^n = n/2 + 2^2(n/2) + 3^2(n/2)... + n^2(n/2) 
= n/2 * n(n+1)(2n+1)/6
= O(n^4)
```

$$ Eq^n = n/2 + 2^2(n/2) + 3^2(n/2)... + n^2(n/2) $$
$$ 
= n/2 * n(n+1)(2n+1)/6
$$
$$= O(n^4)$$


### 4. Logarithmic Time

#### 1. Question 1

```cpp
for(i=1; i<=n; i=i*2){
	cout<<"Hello";
}
```

| **value of i**              | i = 1 or $2^0$ | i = 2 or $2^1$ | i = 4 or $2^2$ | i = 8 or $2^3$ | i = n or $2^k$ |
| --------------------------- | -------------- | -------------- | -------------- | -------------- | -------------- |
| **No of Time gets printed** | 1 times        | 1 times        | 1 times        | 1 times        | 1 times        |
>  **Note: If power is n, it will print n + 1 times**

$$
\begin{align}
n &= 2^k \\
log(n) &= log(2^k) \\
log(n) &= k(log2)\\
k &= log(n)
\end{align}
$$
#### 2. Question 2

```
1, 3, 9, 27, ...n
O(n^3)
```

### 5. Inner Loops is not depending on outer loop

#### Question 1

```cpp
for(i=n/2; i<=n; i++){              // n/2 times
	for(j=1; j<=n/2; j++){         // n/2 times
		for(k=1; k<=n, k++){      // n times
			cout("Hello");       // n/2 * n/2 * n ==> n^3
		}
	}
}
```

#### Question 2

```cpp
for(i=n/2; i<=n; i++){               // n/2 times
	for(j=1; j<=n/2; j++){          // n/2 times
		for(k=1; k<=n, k++){       // n times
			cout("Hello");        // n/2 * n/2 * n ==> n^3
		}
	}
}
```

#### Question 3

```cpp
for(i=n/2; i<=n; i++){                // n/2 times
	for(j=1; j<=n; j=2*j){           // log(n) times
		for(k=1; k<=n, k=2*k){      // log(n) times
			cout("Hello");         // n/2 * log(n) * log(n)
		}                         // => n*log(n)^2
	}
}
```

#### Question 4

```cpp
for(i=1; i<=n; i++){                // n/2 times
	for(j=1; j<=n; j=2*j){           // log(n) times
		for(k=1; k<=n, k=2*k){      // log(n) times
			cout("Hello");         // n/2 * log(n) * log(n)
		}                         // => n*log(n)^2
	}
}
```


# 231, 342, 3304