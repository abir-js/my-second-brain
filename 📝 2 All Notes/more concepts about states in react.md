---
tags:
  - react
status: 🟩
---

2025-08-09        01:28

---
## Components only gets re-rendered when react detects there is a change in state

```tsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState<number>(0);
  console.log("Component is re-rendering");

  function IncreaseCount(): void {
    setCount(25);
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

> Here for multiple clicks on Increase  Count button, it will show "Component is re-rendered" only for first time.

## We can pass normal functions in initial value of useState

```tsx
import { useState } from "react";

function init() {
  console.log("init function is called");
  return Math.random();
}

function Counter() {
  const [count, setCount] = useState<number>(init());
  console.log("Component is re-rendering");

  function IncreaseCount(): void {
    setCount(count + 1);
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

> Here init method will be called each time of re-rendering. So we should pass it as reference

```tsx
const [count, setCount] = useState<number>(init)
```

---
