---
tags:
  - react
status:
---

2025-08-08        13:12

---
# Late state value update in console

```tsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState<number>(0);

  function IncreaseCount(): void {
    setCount(count + 1);
    console.log(count);
  }

  return (
    <div>
      <h3>{count}</h3>
      <button onClick={IncreaseCount}>Increase Count</button>
    </div>
  );
}

export default Counter;
```

You're noticing a common behavior in React. The UI updates correctly, but the `console.log(count)` prints the **previous value**, not the updated one. Here's why:

### 🔄 React state updates are **asynchronous**

When you call `setCount(count + 1)`, React schedules the state update, but doesn't apply it immediately. So, in the next line (`console.log(count)`), `count` still holds the **old value**.

---

### ✅ Correct Way to See the Updated Value

To correctly log the updated value, you can use the `useEffect` hook to track changes in `count`:

```tsx
import { useState, useEffect } from "react";

function Counter() {
  const [count, setCount] = useState<number>(0);

  function IncreaseCount(): void {
    setCount(count + 1);
  }

  useEffect(() => {
    console.log("Count updated:", count);
  }, [count]); // runs whenever 'count' changes

  return (
    <div>
      <h3>{count}</h3>
      <button onClick={IncreaseCount}>Increase Count</button>
    </div>
  );
}
```

---

### 🧠 Summary

- `setCount` doesn’t update `count` immediately.
    
- React batches updates and re-renders after the function completes.
    
- To detect the new value after a state update, use `useEffect`.
    

Let me know if you want a visual illustration or analogy to make this even clearer.

---
