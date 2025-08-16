---
tags:
  - react
status: 🟩
---

2025-08-16        18:32

---
# Forms in React

- Form elements apne **internal states khud maintain karte hai**.
- Unka kuch default behaviour hota hai jo hamare liye desirable nhi hai. Like: 
	- Agar hum form pe events track kare like `onChange`,  `onSubmit` waha as soon as form dubmit pe reload and data los ho jata hai.

- In HTML, form elements such as `<input>`,`<textarea>`, and `select` typically maintain their own state and update it based on user input. 
- In react, mutable state is typically kept in the state property od components and only updated with `setState()`.
- We can combine these two by making the React state be **"single source of truth"**. An input form element whose value is controlled by React in this way is called a **"controlled component".**


## 🔹 1. Controlled Components

Here, React controls the form values via state (`useState`).  
The input’s `value` is tied to React state, and changes happen through `onChange`.

```jsx
import React, { useState } from "react";

export default function MyForm() {
  const [name, setName] = useState("");
  const [age, setAge] = useState("");

  const handleSubmit = (e) => {
    e.preventDefault(); // prevent page reload
    console.log("Submitted:", { name, age });
  };

  return (
    <form onSubmit={handleSubmit}>
      <div>
        <label>Name: </label>
        <input
          type="text"
          value={name}                // controlled by React
          onChange={(e) => setName(e.target.value)} // update state
        />
      </div>

      <div>
        <label>Age: </label>
        <input
          type="number"
          value={age}
          onChange={(e) => setAge(e.target.value)}
        />
      </div>

      <button type="submit">Submit</button>
    </form>
  );
}
```

✅ Pros: React always knows the current value → easier validation, conditional rendering, etc.  
⚠️ Cons: Can be verbose when there are many inputs.

---

## 🔹 2. Uncontrolled Components

Here, the DOM handles the form values. React just _reads_ them using `refs`.

```jsx
import React, { useRef } from "react";

export default function MyForm() {
  const nameRef = useRef();
  const ageRef = useRef();

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log("Submitted:", {
      name: nameRef.current.value,
      age: ageRef.current.value,
    });
  };

  return (
    <form onSubmit={handleSubmit}>
      <div>
        <label>Name: </label>
        <input type="text" ref={nameRef} />
      </div>

      <div>
        <label>Age: </label>
        <input type="number" ref={ageRef} />
      </div>

      <button type="submit">Submit</button>
    </form>
  );
}
```

✅ Pros: Less code for simple forms.  
⚠️ Cons: React doesn’t control values → harder validation/real-time feedback.

---

## 🔹 3. Handling Multiple Inputs (Dynamic Forms)

Instead of one `useState` per field, you can store them in an object:

```jsx
import React, { useState } from "react";

export default function MyForm() {
  const [formData, setFormData] = useState({
    username: "",
    email: "",
    password: ""
  });

  const handleChange = (e) => {
    setFormData({
      ...formData,
      [e.target.name]: e.target.value, // dynamic key
    });
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log("Form Data:", formData);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        name="username"
        placeholder="Username"
        value={formData.username}
        onChange={handleChange}
      />
      <input
        name="email"
        type="email"
        placeholder="Email"
        value={formData.email}
        onChange={handleChange}
      />
      <input
        name="password"
        type="password"
        placeholder="Password"
        value={formData.password}
        onChange={handleChange}
      />

      <button type="submit">Register</button>
    </form>
  );
}
```

---

## 🔹 4. Validation Example

You can add validation inside `handleSubmit` or on every `onChange`.

```jsx
if (!formData.email.includes("@")) {
  alert("Invalid email!");
}
```

---

## 🔹 5. Libraries for Forms

When forms get big/complex, people often use:

- **Formik** (popular, feature-rich)
    
- **React Hook Form** (lightweight, great performance)
    
- **Formik + Yup** (for schema-based validation)
    

---

✨ Summary:

- Use **Controlled Components** when you need React to always know input state (most common).
    
- Use **Uncontrolled Components** for simple forms or when migrating old code.
    
- For large projects → **React Hook Form** or **Formik**.
    

---

Do you want me to show you **how to handle form validation with error messages live (like showing “Name is required” while typing)**?

---
