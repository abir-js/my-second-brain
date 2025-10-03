---
tags:
  - nextjs
status: 🟩
---

2025-10-03        12:15

---
# What are server actions?

They are server side functions that can be called without creating any API routes from react component.

## tRPC
typescript remote procedure call

### Inline server action

```jsx
import React from "react";

const UserForm = () => {
	async function createUser(formData) {
		"use server";
		const name = formData.get("name");
		console.log("Creating user: ", name);
	}
	
	return (
		<form action={createUser}>
			<input name="name" placeholder="John Doe" />
			<button type="submit">Create</button>
		</form>
	);
};

export default UserForm;
```

### Separate Server action
- `actions/index.js`

```jsx
// actions/index.js
"use server";

export async function createUser(formData) {
	const name = formData.get("name");
	console.log("Creating user: ", name);
}
```

![[server-action]]

---
