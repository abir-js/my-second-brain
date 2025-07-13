---
tags:
  - react
status: 🟩
---

2025-07-13        20:34

# What is Title?

```js
const root = ReactDOM.createRoot(document.getElementById("root"));

root.render(H2);
```

- **If we console H2 in browser**

![[consoling-react-element-in-browser.png]]

- Means we can create a React element without using React.createElement()

```js
const H2 = {
    $$typeof: Symbol.for("react.element"),
    type: "h2",
    key: null,
    ref: null,
    props: {
        className: "heading",
        children: "Heading"
    },
    __owner: null,
    _store: {},
}

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(H2);
```

---
### 🔹 Why it matters

React uses `$$typeof: Symbol.for("react.element")` internally to:

- Identify which objects are React elements
    
- Avoid accidental misuse or creation of fake React elements
    
- Ensure safe operations during rendering

---
## Related topics: 

- 

---
