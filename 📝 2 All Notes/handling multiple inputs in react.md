---
tags:
  - react
status: 🟩
---

2025-08-17        20:37

---
In React, when you’re building a form with **multiple inputs** (text, email, password, etc.), you usually want to manage all of them with a **single state object** instead of separate states for each field.

Here’s the step-by-step approach 👇

---

### ✅ Example: Handling Multiple Inputs in React

```jsx
import { useState } from "react";

function MyForm() {
  // Store all inputs in one object
  const [formData, setFormData] = useState({
    name: "",
    email: "",
    password: ""
  });

  // Generic change handler
  const handleChange = (e) => {
    const { name, value } = e.target;

    setFormData((prev) => ({
      ...prev,       // keep old values
      [name]: value  // update only the changed input
    }));
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log("Form Submitted:", formData);
  };

  return (
    <form onSubmit={handleSubmit} className="space-y-4">
      <input
        type="text"
        name="name"
        placeholder="Enter your name"
        value={formData.name}
        onChange={handleChange}
        className="border p-2 rounded"
      />

      <input
        type="email"
        name="email"
        placeholder="Enter your email"
        value={formData.email}
        onChange={handleChange}
        className="border p-2 rounded"
      />

      <input
        type="password"
        name="password"
        placeholder="Enter your password"
        value={formData.password}
        onChange={handleChange}
        className="border p-2 rounded"
      />

      <button type="submit" className="bg-blue-500 text-white px-4 py-2 rounded">
        Submit
      </button>
    </form>
  );
}

export default MyForm;
```

---

### 🔑 Key Points

1. Use **one state object** (`formData`) for all inputs.
    
2. Set each input’s `name` attribute to match the key in your state.
    
3. Use a **generic `handleChange`** that updates the right field dynamically using `[name]: value`.
    
4. Always spread the old state (`...prev`) so you don’t overwrite other fields.
    

---

👉 If you’re working with **checkboxes, radios, or selects**, the logic is the same — you just read `e.target.checked` or `e.target.value` depending on the input type.

---

## ✅ Full Example: Multiple Inputs (text, email, password, checkbox, radio, select)

```jsx
import { useState } from "react";

function MyForm() {
  const [formData, setFormData] = useState({
    name: "",
    email: "",
    password: "",
    agree: false,     // checkbox
    gender: "",       // radio
    country: ""       // select dropdown
  });

  // Generic handler
  const handleChange = (e) => {
    const { name, value, type, checked } = e.target;

    setFormData((prev) => ({
      ...prev,
      [name]: type === "checkbox" ? checked : value
    }));
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log("Form Submitted:", formData);
  };

  return (
    <form onSubmit={handleSubmit} className="space-y-4 p-4 max-w-md mx-auto">
      {/* Text input */}
      <input
        type="text"
        name="name"
        placeholder="Enter your name"
        value={formData.name}
        onChange={handleChange}
        className="border p-2 w-full rounded"
      />

      {/* Email input */}
      <input
        type="email"
        name="email"
        placeholder="Enter your email"
        value={formData.email}
        onChange={handleChange}
        className="border p-2 w-full rounded"
      />

      {/* Password input */}
      <input
        type="password"
        name="password"
        placeholder="Enter your password"
        value={formData.password}
        onChange={handleChange}
        className="border p-2 w-full rounded"
      />

      {/* Checkbox */}
      <label className="flex items-center space-x-2">
        <input
          type="checkbox"
          name="agree"
          checked={formData.agree}
          onChange={handleChange}
        />
        <span>I agree to the terms</span>
      </label>

      {/* Radio buttons */}
      <div>
        <p className="font-medium">Gender:</p>
        <label className="mr-4">
          <input
            type="radio"
            name="gender"
            value="male"
            checked={formData.gender === "male"}
            onChange={handleChange}
          />
          Male
        </label>
        <label>
          <input
            type="radio"
            name="gender"
            value="female"
            checked={formData.gender === "female"}
            onChange={handleChange}
          />
          Female
        </label>
      </div>

      {/* Select dropdown */}
      <select
        name="country"
        value={formData.country}
        onChange={handleChange}
        className="border p-2 w-full rounded"
      >
        <option value="">Select Country</option>
        <option value="india">India</option>
        <option value="usa">USA</option>
        <option value="uk">UK</option>
      </select>

      {/* Submit button */}
      <button
        type="submit"
        className="bg-blue-500 text-white px-4 py-2 rounded"
      >
        Submit
      </button>
    </form>
  );
}

export default MyForm;
```

---

### 🔑 Key Notes

1. **Checkboxes:** use `checked` instead of `value`.
    
    ```js
    [name]: type === "checkbox" ? checked : value
    ```
    
2. **Radio buttons:** same `name`, different `value`. Only one can be selected.
    
    - You check with `formData.gender === "male"`.
        
3. **Select dropdowns:** just bind `value` like text inputs.
    

---

👉 This setup scales very well — you can add more fields without writing new handlers.

Would you like me to also show you a **dynamic form** version (like handling inputs when you don’t know the field names in advance, e.g., from an API)?

---
## "name" attribute

Great question 👌 — the `name` attribute is **super important** when handling multiple inputs in React.

---

### 🔑 Rule of Thumb

The `name` attribute should match the **key in your state object** (`formData`).  
That way, your generic `handleChange` can automatically update the right field.

---

### Example

```jsx
const [formData, setFormData] = useState({
  name: "",
  email: "",
  password: "",
  agree: false,
  gender: "",
  country: ""
});
```

- For `formData.name` → input gets `name="name"`.
    
- For `formData.email` → input gets `name="email"`.
    
- For `formData.agree` → checkbox gets `name="agree"`.
    
- For `formData.gender` → radio buttons get `name="gender"`.
    
- For `formData.country` → select gets `name="country"`.
    

```jsx
<input type="text" name="name" value={formData.name} onChange={handleChange} />
<input type="email" name="email" value={formData.email} onChange={handleChange} />
<input type="password" name="password" value={formData.password} onChange={handleChange} />

<input type="checkbox" name="agree" checked={formData.agree} onChange={handleChange} />

<input type="radio" name="gender" value="male" checked={formData.gender === "male"} onChange={handleChange} />
<input type="radio" name="gender" value="female" checked={formData.gender === "female"} onChange={handleChange} />

<select name="country" value={formData.country} onChange={handleChange}>
  <option value="india">India</option>
  <option value="usa">USA</option>
</select>
```

---

### 🚀 Why this works

Because in `handleChange`, you’re using:

```js
setFormData((prev) => ({
  ...prev,
  [name]: type === "checkbox" ? checked : value
}));
```

The `name` acts like the **key selector** that tells React _which field in `formData` should be updated_.

---

👉 So: **always give the same `name` as the state property** you want to update.

Do you want me to also show you what happens if you **don’t use the right name** (so you can see why it breaks)?