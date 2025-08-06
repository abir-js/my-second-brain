---
tags:
  - react
status: 🟩
---

2025-08-06        11:03

---
`useRef` is a Hook in React that provides a way to **persist values between renders** **without causing a re-render** when the value changes. It's commonly used for:

1. **Accessing DOM elements directly**
    
2. **Storing mutable values** that don’t trigger a re-render when changed (like timers, previous values, etc.)
    

---

### ✅ Syntax:

```js
const myRef = useRef(initialValue);
```

---

## 🧠 1. **Accessing DOM Elements**

You can use `useRef` to directly access a DOM element, like an input box:

```jsx
import React, { useRef } from "react";

function InputFocus() {
  const inputRef = useRef(null);

  const focusInput = () => {
    inputRef.current.focus(); // Access the DOM node and focus it
  };

  return (
    <>
      <input ref={inputRef} type="text" />
      <button onClick={focusInput}>Focus Input</button>
    </>
  );
}
```

---

## 🧠 2. **Storing Mutable Values (without causing re-render)**

```jsx
import React, { useRef, useState } from "react";

function TimerExample() {
  const countRef = useRef(0);
  const [ignored, forceRender] = useState(false); // to force render if needed

  const increment = () => {
    countRef.current += 1;
    console.log("Count:", countRef.current);
  };

  return (
    <div>
      <p>Current count (check console): {countRef.current}</p>
      <button onClick={increment}>Increment</button>
      <button onClick={() => forceRender(!ignored)}>Force Render</button>
    </div>
  );
}
```

> `countRef.current` is mutable, but changing it does **not** trigger re-render. If you want to see it updated in UI, use a `useState`.

---

## 🧠 3. **Tracking Previous State Value**

```jsx
import React, { useEffect, useRef, useState } from "react";

function PreviousValueExample() {
  const [count, setCount] = useState(0);
  const prevCountRef = useRef();

  useEffect(() => {
    prevCountRef.current = count;
  }, [count]);

  return (
    <div>
      <p>Current: {count}</p>
      <p>Previous: {prevCountRef.current}</p>
      <button onClick={() => setCount(c => c + 1)}>Increment</button>
    </div>
  );
}
```

---

## ⚠️ Key Points

|Feature|`useRef`|
|---|---|
|Triggers re-render?|❌ No|
|Access DOM?|✅ Yes|
|Keep value between renders?|✅ Yes|
|Alternative to class `this.someVar`|✅ Yes|
|Good for timers/intervals?|✅ Yes|

---

