---
tags:
  - derivatives
status:
---

2025-09-13        12:55

---
# 📘 Derivatives Cheat Sheet (with Examples)

---

## 🔹 1. Basic Rules

- **Constant Rule:**  
  `d/dx(c) = 0`  
  👉 Example: `d/dx(5) = 0`

- **Power Rule:**  
  `d/dx(x^n) = n * x^(n-1)`  
  👉 Example: `d/dx(x^4) = 4x^3`

- **Constant Multiple Rule:**  
  `d/dx[c * f(x)] = c * f'(x)`  
  👉 Example: `d/dx(7x^2) = 14x`

- **Sum/Difference Rule:**  
  `d/dx[f(x) ± g(x)] = f'(x) ± g'(x)`  
  👉 Example: `d/dx(x^3 + x^2) = 3x^2 + 2x`

---

## 🔹 2. Product & Quotient

- **Product Rule:**  
  `d/dx[u * v] = u'v + uv'`  
  👉 Example: `d/dx(x^2 * sin(x)) = 2x * sin(x) + x^2 * cos(x)`

- **Quotient Rule:**  
  `d/dx[u/v] = (u'v - uv') / v^2`  
  👉 Example: `d/dx(x^2 / (x+1)) = ((2x)(x+1) - x^2 * 1) / (x+1)^2`

---

## 🔹 3. Chain Rule (Composite Functions)

- **Chain Rule:**  
  `d/dx[f(g(x))] = f'(g(x)) * g'(x)`  
  👉 Example: `d/dx(sin(x^2)) = cos(x^2) * 2x`

---

## 🔹 4. Common Derivatives

- **Power Function:**  
  `d/dx(x^n) = n * x^(n-1)`  
  👉 Example: `d/dx(x^3) = 3x^2`

- **Exponential:**  
  `d/dx(e^x) = e^x`  
  👉 Example: `d/dx(5e^x) = 5e^x`

- **Logarithm:**  
  `d/dx(ln x) = 1/x`  
  👉 Example: `d/dx(ln(3x)) = 1/x`

- **Sine:**  
  `d/dx(sin x) = cos x`  
  👉 Example: `d/dx(sin(2x)) = cos(2x) * 2`

- **Cosine:**  
  `d/dx(cos x) = -sin x`  
  👉 Example: `d/dx(cos(3x)) = -sin(3x) * 3`

- **Tangent:**  
  `d/dx(tan x) = sec^2 x`  
  👉 Example: `d/dx(tan(5x)) = 5 * sec^2(5x)`

---

## 🔹 5. Special Cases

- **General Exponential:**  
  `d/dx(a^x) = a^x * ln(a)`  
  👉 Example: `d/dx(2^x) = 2^x * ln(2)`

- **Logarithm (base a):**  
  `d/dx(log_a x) = 1 / (x * ln(a))`  
  👉 Example: `d/dx(log_10 x) = 1 / (x * ln(10))`

---

✅ **Tip for Newton-Raphson:**  
You mainly need **power rule, product rule, and chain rule** for most problems.


---
