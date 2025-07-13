---
tags:
  - react
status:
---

2025-07-13        17:26

### ✅ What is `React.createElement`?

`React.createElement` is the fundamental API used to create React elements **without using JSX**. JSX is just syntactic sugar that gets compiled to `React.createElement` calls.

---

### ✅ Syntax:

```js
React.createElement(type, props, ...children)
```

- `type`: A string like `'div'`, `'h1'`, or a component function/class.
    
- `props`: An object containing the attributes/props you want to set (or `null`).
    
- `children`: Any child elements or text (can be multiple).
    

---

### ✅ Example Without JSX:

```js
const element = React.createElement(
  'h1',
  { className: 'greeting' },
  'Hello, world!'
);
```

This is equivalent to:

```jsx
<h1 className="greeting">Hello, world!</h1>
```

---

### ✅ Example with Nested Elements:

```js
const element = React.createElement(
  'div',
  null,
  React.createElement('h1', null, 'Hello'),
  React.createElement('p', null, 'This is a paragraph')
);
```

This is equivalent to:

```jsx
<div>
  <h1>Hello</h1>
  <p>This is a paragraph</p>
</div>
```

---

### ✅ When to Use `React.createElement`?

- If you're not using JSX (e.g., in environments where JSX isn't supported).
    
- When building low-level libraries.
    
- When transpilation is not desired (e.g., no Babel setup).
    

---
## Related topics: 

- 

---
