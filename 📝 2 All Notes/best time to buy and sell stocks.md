---
tags:
  - array
  - java
  - dsa
status: 🟩
---

2025-08-31        00:07

---
# Buy and Sell Stocks?

## Problem Statement

You are given an array `prices` where `prices[i]` is the price of a given stock on the `ith` day.

You want to maximize your profit by choosing a **single day** to buy one stock and choosing a **different day in the future** to sell that stock.

Return _the maximum profit you can achieve from this transaction_. If you cannot achieve any profit, return `0`.

**Example 1:**

**Input:** prices = [7,1,5,3,6,4]
**Output:** 5
**Explanation:** Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

**Example 2:**

**Input:** prices = [7,6,4,3,1]
**Output:** 0
**Explanation:** In this case, no transactions are done and the max profit = 0.

**Constraints:**

- `1 <= prices.length <= 105`
- `0 <= prices[i] <= 104`

## Strategy:

```java
profit = sellingPrice - buyPrice
buyPrice = min(price)
sellPrice = currentPrice

buyPrice = INTEGER.max
maxProffit = 0

for(int i = 0 to n){
	if (buyPrice < sellPrice){
		maxProfit = max(buyPrice - sellPrice)
	} else {
		buyPrice = sellingPrice
	}
}

```

## Code: 

```java

public class buyAndSellStock {
	public static int maxProfit(int[] prices) {
		int buyPrice = Integer.MAX_VALUE;
		int maxProfit = 0;
		for(int i = 0; i<prices.length; i++){
			if(buyPrice < prices[i]) { //profit
				int profit = prices[i] - buyPrice; // today's profit
				maxProfit = Math.max(maxProfit, profit);
			} else {
				buyPrice = prices[i];
			}
		}
		return maxProfit;
	}
	public static void main(String[] args) {
		int[] prices = {7, 1, 5, 3, 6, 4};
		System.out.println("Max profit: "+ maxProfit(prices));
	}
}
```

---
