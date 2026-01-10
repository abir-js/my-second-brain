---
tags:
  - genai
status: 🟩
---

2026-01-10        19:25

---
# find distances between two vectors?

## 1. Euclidean Distance

## Euclidean Distance (Vectors)

The **Euclidean distance** between two vectors is the straight-line distance between them.

### Formula
For two vectors  
**x = (x₁, x₂, …, xₙ)** and **y = (y₁, y₂, …, yₙ)**

$$
d(x, y) = \sqrt{\sum_{i=1}^{n} (x_i - y_i)^2}
$$

### Example
Let  
**x = (2, 3)**  
**y = (5, 7)**
$$
\
\begin{aligned}
d &= \sqrt{(2 - 5)^2 + (3 - 7)^2} \\
  &= \sqrt{9 + 16} \\
  &= \sqrt{25} \\
  &= 5
\end{aligned}
\
$$
**Euclidean distance = 5**


## Cosine Similarity (Vectors)

Cosine similarity measures how similar two vectors are by checking the angle between them.

### Formula
cos(θ) = (x · y) / (|x| |y|)

Where:
- x · y = x1.y1 + x2.y2 + ... + xn.yn
- |x| = sqrt(x1² + x2² + ... + xn²)
- |y| = sqrt(y1² + y2² + ... + yn²)

---

### Example
x = (1, 2)  
y = (2, 3)

Step 1: Dot product  
x · y = (1×2) + (2×3) = 2 + 6 = 8

Step 2: Magnitudes  
|x| = sqrt(1² + 2²) = sqrt(5)  
|y| = sqrt(2² + 3²) = sqrt(13)

Step 3: Cosine similarity  
cos(θ) = 8 / (sqrt(5) × sqrt(13))  
cos(θ) ≈ 0.99

---

### Interpretation
- 1 → vectors point in the same direction  
- 0 → vectors are perpendicular  
- −1 → vectors point in opposite directions


---
