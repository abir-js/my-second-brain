---
tags:
  - react
status: 🟩
---

2025-08-09        12:14

---
In React, when you store an **object in state**, you usually use `useState` with an initial object and update it carefully — because React **doesn’t automatically merge** updates for objects (unlike class components’ `setState`).

---

### Example: Object in State

```jsx
import { useState } from "react";

function UserProfile() {
  const [user, setUser] = useState({
    name: "Abir",
    age: 20,
    city: "Kolkata"
  });

  const updateCity = () => {
    setUser(prevUser => ({
      ...prevUser,   // copy existing properties
      city: "Delhi" // update only the city
    }));
  };

  return (
    <div>
      <h2>{user.name}</h2>
      <p>{user.age} years old</p>
      <p>Lives in {user.city}</p>
      <button onClick={updateCity}>Move to Delhi</button>
    </div>
  );
}

export default UserProfile;
```

---

### Key Points

1. **Spread operator** is used (`...prevUser`) to keep other fields intact.
    
2. **Never mutate state directly** (e.g., `user.city = 'Delhi'`) — this breaks reactivity.
    
3. **Updating nested objects** requires spreading at each level.
    

---

### Nested Object Example

```jsx
setUser(prevUser => ({
  ...prevUser,
  address: {
    ...prevUser.address,
    city: "Delhi"
  }
}));
```

---

Gotcha — you’re asking why we can’t just do:

```js
user.city = "Delhi";
setUser(user);
```

or even just:

```js
user.city = "Delhi";
```

without spreading.

---

The short answer:

> **React only triggers a re-render when the state value’s reference changes**.  
> If you mutate the existing object, the reference stays the same, so React thinks “nothing changed” and skips rendering.

---

### Why spreading works

When you do:

```js
setUser(prev => ({
  ...prev,
  city: "Delhi"
}));
```

you’re creating a **brand new object** with a **different reference** in memory.  
React compares the new reference to the old one (`===` check). Since they’re different, it re-renders.

---

### Why direct mutation fails

```js
prev.city = "Delhi"; // modifies the same object in memory
setUser(prev);       // same reference → React sees no change
```

React internally checks:

```js
if (newState === oldState) return; // skip re-render
```

Mutating doesn’t change the reference, so `===` is still `true`.

---

### TL;DR

- React state is immutable — you must return a new object/array to update it.
    
- Spreading (`...`) is the easiest way to clone the old state and change only what’s needed.
    
- Mutating in place means React won’t know it should re-render.
    

---
