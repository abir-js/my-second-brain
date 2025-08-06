---
tags:
  - react
status: 🟩
---

2025-08-06        17:33

---
### 🧠 `useMemo` in React — Explained Simply

---

### ✅ What is `useMemo`?

`useMemo` is a **React Hook** that **memorizes (caches) the result of a computation**, so the function doesn't run again **unless its dependencies change**.

It helps **optimize performance** by **avoiding expensive re-computation** during re-renders.

---

### 📦 Syntax

```js
const memoizedValue = useMemo(() => {
  // compute something expensive
  return result;
}, [dependencies]);
```

---

### 🧠 When to Use `useMemo`

Use `useMemo` when:

- You have **expensive calculations** (e.g., filtering, sorting, loops).
    
- The result **doesn’t need to change on every render**.
    
- The component **re-renders often**, but the inputs to the logic **don’t change often**.
    

---

### ✅ Example: Expensive Computation

```jsx
import React, { useMemo, useState } from "react";

function ExpensiveComponent({ number }) {
  const [count, setCount] = useState(0);

  const expensiveCalculation = (num) => {
    console.log("Calculating...");
    let result = 0;
    for (let i = 0; i < 1e7; i++) {
      result += num;
    }
    return result;
  };

  const computedValue = useMemo(() => {
    return expensiveCalculation(number);
  }, [number]); // only recompute when 'number' changes

  return (
    <div>
      <h2>Expensive Value: {computedValue}</h2>
      <button onClick={() => setCount(count + 1)}>Re-render ({count})</button>
    </div>
  );
}
```

### 🧪 Behavior:

- `expensiveCalculation()` only runs **when `number` changes**.
    
- Clicking the button triggers a re-render, but the **cached value is reused**.
    

---

### ⚠️ When **not** to use `useMemo`

- Don’t use it **everywhere** — it's only helpful for **truly expensive logic**.
    
- **Simple values** don’t need memoization — it adds overhead.
    

---

### 🔍 Summary

|Feature|`useMemo`|
|---|---|
|Returns|**Memoized** result of a function|
|Triggers re-run|When **dependencies change**|
|Used for|Expensive calculations, derived data|
|Not for|Skipping component re-renders (use `React.memo` for that)|

---

Let me know if you want to compare `useMemo` with `useCallback`, or want real-world examples like sorting/filtering large lists!

---
