---
tags:
  - java
  - dsa
  - array
status: 🟩
---

2025-08-26        08:57

---
# Trapping rainwater problem?

**Given n non-negative integers representing an elevation map where the width of each bar is 1, compute how much water it can trap after raining.**

![[trapping-rainwater]]

`height = [4, 2, 0, 6, 3, 2, 5]`


![[no-of-bars-in-rainwater-problem]]


*water stored on each bar = minimum (height of left tallest bar, height of right tallest bar) - bar height*

![[trapping-rainwater-solution]]


## How to solve using code

![[trapping-rainwater-auxilary-arrays]]

![[trappting-rainwater-leetcode.png]]

```java
class Solution {
    public int trap(int[] height) {
        int leftMax[] = new int[height.length];
        int rightMax[] = new int[height.length];

        leftMax[0] = height[0];
        for (int i = 1; i < height.length; i++) {
            leftMax[i] = Math.max(height[i], leftMax[i - 1]);
        }

        rightMax[height.length - 1] = height[height.length - 1];
        for (int i = height.length - 2; i >= 0; i--) {
            rightMax[i] = Math.max(height[i], rightMax[i + 1]);
        }

        int trappedWater = 0;
        for (int i = 0; i < height.length; i++) {
            int waterLevel = Math.min(leftMax[i], rightMax[i]);
            trappedWater += waterLevel - height[i];
        }
        return trappedWater;
    }
}
```


---
