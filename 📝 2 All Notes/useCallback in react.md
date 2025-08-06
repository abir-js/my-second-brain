---
tags:
  - react
status: 🟩
---

2025-08-06        18:39

---
`useCallback` is a React **Hook** that lets you **memoize a callback function** — in other words, it returns a **memoized version of the function** that only changes if its dependencies change.

---

### 📌 Syntax

```js
const memoizedCallback = useCallback(() => {
  // callback logic
}, [dependency1, dependency2]);
```

---

### 🧠 Why use `useCallback`?

- In React, **functions are re-created** on every render.
    
- This can cause **unnecessary re-renders** of child components that rely on **reference equality** (`===`) or are wrapped in `React.memo`.
    
- `useCallback` helps prevent that by **caching the function**.
    

---

### ✅ Example

```jsx
import { useState, useCallback } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  const increment = useCallback(() => {
    setCount((prev) => prev + 1);
  }, []); // no dependencies = only created once

  return (
    <div>
      <p>Count: {count}</p>
      <Button onClick={increment} />
    </div>
  );
}

const Button = React.memo(({ onClick }) => {
  console.log('Button re-rendered');
  return <button onClick={onClick}>Increment</button>;
});
```

> Without `useCallback`, the `increment` function would be recreated every render, causing the `Button` to re-render even if its props didn’t change.

---

### 📦 When to use it?

- When you pass **functions to memoized child components** (`React.memo`).
    
- When you want to **avoid re-creating functions unnecessarily** in performance-critical code.
    

---

### ⚠️ Don't overuse!

Using `useCallback` has **a small cost**, so **only use it when needed**, especially in large lists or components with performance bottlenecks.

---

Would you like a visual example (e.g., with a parent and child component showing unnecessary renders)?

---
