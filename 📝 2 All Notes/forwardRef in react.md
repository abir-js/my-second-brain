---
tags:
  - react
status: 🟩
---

2025-08-06        17:29

---
### 🔁 `forwardRef` in React — Explained Simply

`forwardRef` is a **React utility** that lets you **pass a `ref` from a parent component to a child functional component**, especially when the child needs to expose a DOM element (like an `<input>` or `<div>`) to the parent.

---

### 🤯 The Problem

Normally, `ref` only works on **DOM elements or class components**, not on custom function components.

```jsx
function MyInput() {
  return <input />;
}

const inputRef = useRef();
<MyInput ref={inputRef} /> // ❌ This won't work – React can't assign ref to a function component
```

---

### ✅ The Solution: `forwardRef`

You can wrap your function component using `React.forwardRef` to **forward the ref** to a child DOM node.

---

### ✅ Example

#### 🔧 Child Component (forwarding the ref)

```jsx
import React, { forwardRef } from "react";

const MyInput = forwardRef((props, ref) => {
  return <input ref={ref} {...props} />;
});
```

#### 💡 Parent Component

```jsx
import React, { useRef } from "react";
import MyInput from "./MyInput";

export default function App() {
  const inputRef = useRef();

  const focusInput = () => {
    inputRef.current.focus(); // works!
  };

  return (
    <>
      <MyInput ref={inputRef} placeholder="Type here" />
      <button onClick={focusInput}>Focus</button>
    </>
  );
}
```

---

### 🔍 Why Use `forwardRef`?

|Use Case|Example|
|---|---|
|Controlling input from parent|`.focus()` or `.scrollIntoView()`|
|Creating reusable input components|`<CustomInput ref={...} />`|
|Library components (like buttons, modals)|You want parent control of child DOM|

---

### 🧠 Quick Recap

|Feature|`forwardRef`|
|---|---|
|Works with|Function components|
|Purpose|Allow parent to access a child DOM node|
|Used with|`useRef()`|
|Triggers re-render?|❌ Not by itself|

---

Let me know if you want to combine this with `useImperativeHandle` to expose **custom methods**!
---
