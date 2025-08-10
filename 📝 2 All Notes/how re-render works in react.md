---
tags:
  - react
status: 🟩
---

2025-08-09        00:46

---
# How re-rendering works in react?

```tsx
import { useState } from "react";

function Counter() {
  const [count, setCount] = useState<number>(0); // Initialization
  console.log("Component is rerendered");
  console.log({count});

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

> When `setState` is called, the whole component gets re-rendered, accept the `useState()` declaration line.

> Upon each `Increase Count` button press, the component will get re-rendered. 

![[Pasted image 20250809010527.png]]

> Here you can see, `setCount(count + 1)` does not immediately changes `count` value. The `count` value is getting changed on re-render.

There are two stages: 
1. `setCount()` method call
2. Re-rendering of component - here count value is changing.


---
