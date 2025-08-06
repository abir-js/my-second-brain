---
tags:
  - react
status: 🟩
---

2025-08-06        22:14

---
# Import-Export

## Import

```jsx
import Title from "./Title.jsx";
```
## Default Export

```jsx
export default Title;
```
## Named Export

```jsx
export { Title };
//or
import { Title } from "./Title.jsx";
```

- In summary, **named exports** are useful when you want to **export multiple**
**values** and **import them with their specific names**, while **default exports** are
handy for **exporting a single value** and **giving it a custom name** when
importing. The choice between the two depends on the structure and
requirements of your codebase.


---
