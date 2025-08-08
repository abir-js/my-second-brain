---
tags:
  - react
status: 🟩
---

2025-08-08        12:30

---
# States in React

- The state is a built-in **React object** that is used to contain data or information about the component.
- A component's state can change over time; whenever it changes, the component re-renders.

```tsx
function Counter() {
  let count: number = 0;

  function increment(): void {
    count++;
    console.log(count);
  }

  return (
    <div>
      <h3>count: {count}</h3>
      <button onClick={increment}>Increase Count</button>
    </div>
  );
}

export default Counter;
```

- The count is increasing, but it is not showing on UI. No Update in DOM.

---

### 🔍 What does "immutable" mean here?

When a component receives `props`, they are **read-only**. If you try to modify them directly (e.g., `props.name = "John"`), React won’t stop you immediately with an error, but:

1. It violates React's core principle of **unidirectional data flow**.
    
2. It can lead to unexpected bugs.
    
3. You’ll get a warning in strict mode or TypeScript/ESLint might complain.
    

---

### ✅ Correct usage:

Props should only be **read and used**, not modified.

```tsx
function Welcome(props: { name: string }) {
  return <h1>Hello, {props.name}!</h1>;
}
```

If you want to change the value shown, that change should happen **in the parent**, and the new value should be passed down as a new prop.

---

### ❌ Don't do this:

```tsx
function Wrong(props: { name: string }) {
  props.name = "Jane"; // ❌ Not allowed — modifying props directly
  return <h1>{props.name}</h1>;
}
```

---

### If you need to "modify" a prop…

Use **`useState`** or **derive new values**:

```tsx
function EditableName(props: { name: string }) {
  const [name, setName] = useState(props.name); // local state initialized from prop

  return <input value={name} onChange={(e) => setName(e.target.value)} />;
}
```

---

Let me know if you want a visual diagram of how data flows in React (parent → child via props).