---
tags:
  - react
status: 🟩
---

2025-08-07        11:04

---
### 🔍 What is Prop Drilling in React?

**Prop drilling** refers to the process of passing data (props) **from a parent component to a deeply nested child component** — even when **intermediate components don’t need that data**, but must pass it down anyway.

---

### 🧱 Example of Prop Drilling

```jsx
function App() {
  const user = { name: 'Abir' };

  return <Parent user={user} />;
}

function Parent({ user }) {
  return <Child user={user} />;
}

function Child({ user }) {
  return <GrandChild user={user} />;
}

function GrandChild({ user }) {
  return <p>Hello, {user.name}</p>;
}
```

> 🔁 `user` is passed through `Parent` and `Child`, even though only `GrandChild` actually uses it.

---

### 🚨 Problems with Prop Drilling

- **Redundant props** in intermediate components
    
- **Harder to maintain** and refactor as the app grows
    
- **Tight coupling** between components
    

---

### ✅ Solutions to Avoid Prop Drilling

#### 1. **React Context API** (for global/shared state)

```jsx
const UserContext = React.createContext();

function App() {
  const user = { name: 'Abir' };

  return (
    <UserContext.Provider value={user}>
      <Parent />
    </UserContext.Provider>
  );
}

function GrandChild() {
  const user = React.useContext(UserContext);
  return <p>Hello, {user.name}</p>;
}
```

No more drilling through `Parent` and `Child`.

---

#### 2. **State Management Libraries**

- Redux
    
- Zustand
    
- Recoil
    
- Jotai

Useful for large applications where shared state is complex.

---

#### 3. **Component Composition / Callbacks**

Sometimes you can avoid prop drilling by **lifting state up** and passing **callbacks down** instead of raw data.

---

### 🧠 TL;DR

|🔧 Term|📖 Meaning|
|---|---|
|**Prop Drilling**|Passing props through intermediate components that don’t need them|
|**Problem**|Clutters components and makes code harder to manage|
|**Solutions**|Context API, state management libs, component restructuring|

---
