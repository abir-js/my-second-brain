---
tags:
  - react
status: 🟩
---

2025-08-09        01:12

---
# Callback in setState()

```tsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState<number>(0);

  function IncreaseCount(): void {
    setCount(count + 1);
    setCount(count + 1);
  }

  return (
    <div>
      <h3>{count}</h3>
      <button 
        onClick={IncreaseCount}
        >
        Increase Count
      </button>
    </div>
  );
}

export default Counter;
```

## Why is it updating only once?

> In React, **state updates via `setState` (like `setCount`) are asynchronous and batched**. When you call:

```ts
setCount(count + 1);
setCount(count + 1);
```

Both calls read the **same `count` value from the current render**, not the updated one. React batches them together, so the second call doesn’t see the increment from the first call — it’s as if both were:

```ts
setCount(0 + 1);
setCount(0 + 1);
```

Result: The state only increases by **1**, not **2**.

To correctly increment twice, you need the functional form, which uses the most recent state:

```ts
setCount(prev => prev + 1);
setCount(prev => prev + 1);
```

This way, the second update gets the already updated value from the first update, giving the expected result.

Would you like me to also explain **why React batches these updates** in modern versions?

---
