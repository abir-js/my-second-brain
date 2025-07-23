---
tags:
  - react
status: 🟩
---

2025-07-21        01:29

---
# What is useState hook?

> "`useState` is a React hook that allows functional components to manage local state. It returns a pair: the current state value, and a function to update it. When the state is updated, the component re-renders to reflect the change."

---

### ✅ Example You Can Say or Write in an Interview:

```jsx
import { useState } from "react";

function Example() {
  const [count, setCount] = useState(0); // count is the state variable

  return (
    <div>
      <p>Clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click
      </button>
    </div>
  );
}
```

Then explain:

> “Here, I used `useState(0)` to initialize a state variable `count` with value `0`. `setCount` updates it. When the button is clicked, `setCount(count + 1)` increments the value and the UI updates.”

---

### ✅ Common Follow-up Questions & How to Answer:

#### 🔹 **Q: Can you use multiple `useState` in one component?**

> "Yes, you can use as many `useState` calls as needed. Each call manages separate state."

```jsx
const [name, setName] = useState('');
const [age, setAge] = useState(0);
```

---

#### 🔹 **Q: What happens when you update state?**

> "React re-renders the component with the new state. It doesn’t mutate the state directly — it triggers a fresh render."

---

#### 🔹 **Q: What’s the difference between `useState` and `useReducer`?**

> "`useState` is simpler and best for managing simple values. `useReducer` is better for complex state logic like toggling multiple values or handling actions."

---
