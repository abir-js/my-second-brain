---
tags:
  - react
status: 🟩
---

2025-08-16        18:16

---
In React, **functions can be passed as props** to child components so the child can "call back" into the parent. This is a common pattern for handling events, updating state in the parent, or sharing logic.

---

### 🔹 Example 1: Passing a function as a prop

```jsx
// Parent.js
import React, { useState } from "react";
import Child from "./Child";

export default function Parent() {
  const [count, setCount] = useState(0);

  // function to increment count
  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <h1>Count: {count}</h1>
      {/* Pass function as prop */}
      <Child onIncrement={increment} />
    </div>
  );
}
```

```jsx
// Child.js
import React from "react";

export default function Child({ onIncrement }) {
  return (
    <button onClick={onIncrement}>
      Increase Count
    </button>
  );
}
```

✅ When the button in **Child** is clicked, it calls `onIncrement`, which updates the state in **Parent**.

---

### 🔹 Example 2: Passing arguments to functions

You can pass a function that accepts parameters:

```jsx
// Parent.js
import React, { useState } from "react";
import Child from "./Child";

export default function Parent() {
  const [name, setName] = useState("Guest");

  const changeName = (newName) => {
    setName(newName);
  };

  return (
    <div>
      <h1>Hello, {name}!</h1>
      <Child onChangeName={changeName} />
    </div>
  );
}
```

```jsx
// Child.js
import React from "react";

export default function Child({ onChangeName }) {
  return (
    <div>
      <button onClick={() => onChangeName("Abir")}>Set Name to Abir</button>
      <button onClick={() => onChangeName("Alice")}>Set Name to Alice</button>
    </div>
  );
}
```

---

### 🔹 Example 3: Inline function props

You can also directly pass inline functions:

```jsx
<Child onClick={() => console.log("Child clicked!")} />
```

---

### ✨ Key Points:

- Functions as props let **children communicate with parents**.
    
- Great for **event handling** (e.g., clicks, form submissions).
    
- Helps keep **state in parent** but allow children to update it.
    
- Functions passed as props are often called **callbacks**.
    

---

Do you want me to also explain **how to prevent unnecessary re-renders** when passing functions as props (using `useCallback`)?

---
