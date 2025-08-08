---
tags:
  - react
status: 🟩
---

2025-08-08        11:25

---
In React, **handling events** works similarly to handling events in plain HTML/JS, but with a few **React-specific differences**.

---

### ✅ Basic Syntax

```jsx
function MyButton() {
  function handleClick() {
    alert('Button was clicked!');
  }

  return <button onClick={handleClick}>Click me</button>;
}
```

---

### 🧠 Key Differences from HTML/JS:

|HTML|React|
|---|---|
|`onclick="..."`|`onClick={...}` (camelCase)|
|`return false` to stop|Use `event.preventDefault()`|
|Plain JS functions|Use arrow functions or class methods|

---

### 🧪 Example with `event` object:

```jsx
function MyInput() {
  function handleChange(event) {
    console.log('Input value:', event.target.value);
  }

  return <input type="text" onChange={handleChange} />;
}
```

---

### ⚡ Common Events in React:

|Event Name|Description|
|---|---|
|`onClick`|When an element is clicked|
|`onChange`|For input, textarea, select changes|
|`onSubmit`|When a form is submitted|
|`onMouseEnter` / `onMouseLeave`|Mouse hover events|
|`onKeyDown` / `onKeyUp`|Keyboard interaction|

---

### 🔁 Passing Arguments to Event Handlers

```jsx
function handleClick(name) {
  alert(`Hello, ${name}`);
}

<button onClick={() => handleClick('Abir')}>Greet</button>
```

---

### 💡 Example: Form Handling

```jsx
function FormExample() {
  function handleSubmit(event) {
    event.preventDefault(); // stops form from reloading page
    alert('Form submitted!');
  }

  return (
    <form onSubmit={handleSubmit}>
      <button type="submit">Submit</button>
    </form>
  );
}
```

---

## **Event Object**

In React, when you handle an event (like a button click), React passes an **event object** as an argument to your handler function. This event object contains **information about the event** — what triggered it, mouse position, keys pressed, etc.

---

### ✅ Example:

```jsx
function handleClick(e) {
  console.log("Button clicked!");
  console.log(e); // This is the event object
}

function App() {
  return <button onClick={handleClick}>Click me</button>;
}
```

### ✅ Output in console:

- `"Button clicked!"`
    
- A **SyntheticEvent** object (React’s wrapper around the browser’s native event)
    

---

### 🔍 What's in the `event` object?

```js
console.log(e.type);       // e.g., "click"
console.log(e.target);     // DOM element that triggered the event
console.log(e.currentTarget); // The element the handler is bound to
```

---

### 📌 React uses SyntheticEvent

- React wraps the native DOM event in a `SyntheticEvent` to make it consistent across all browsers.
    
- But you can still access the **native event** via `e.nativeEvent`.
    

---

### 🧠 Common Use Case: Preventing default behavior

```jsx
function handleSubmit(e) {
  e.preventDefault(); // stops form from refreshing the page
  console.log("Form submitted");
}
```

---

### 💡 If you're using arrow functions

```jsx
<button onClick={(e) => handleClick(e)}>Click</button>
```

Or, if passing custom arguments:

```jsx
function handleClick(name, e) {
  console.log("Hello " + name);
  console.log(e); // event object
}

<button onClick={(e) => handleClick("Abir", e)}>Click</button>
```

---
