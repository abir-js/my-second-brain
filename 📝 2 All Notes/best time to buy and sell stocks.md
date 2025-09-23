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

![[buy-and-sell-stocks]]

## Code: 

```java

class Solution {
	public int maxProfit(int[] prices) {
		int buyPrice = prices[0];
		int profit = 0;
		for (int x : prices) {
			if (x < buyPrice) { // agar current price buyPrice se kam hoga to current price pe buy karo
				buyPrice = x; 
			} else { // agar current price buy price se bada hai to zyada profit pe sell karo
				int currProfit = x - buyPrice;
				if (currProfit > profit) {
					profit = currProfit;
				}
			}
		}
		return profit;
	}
}
```

---
