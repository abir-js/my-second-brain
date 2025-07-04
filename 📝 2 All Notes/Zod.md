---
tags:
  - backend
  - express
status: 🟩
---

2025-07-04        11:56

# What is Title?

- Validate User age

```js
import { z, ZodError } from "zod";
const ageSchema = z.number().min(18).max(100).int();

const userAge = 17;
const { data, error, success } = ageSchema.safeParse(userAge);

try {
  const parseUserAge = ageSchema.parse(userAge);
  console.log(parseUserAge); //? Success Message
} catch (error) {
  //* Instance is a Javascript operator used to check if a object is an instance of a specific class or constructor.
  if (error instanceof ZodError) {
    console.log(error.issues[0].message); //? Display the error message only
  } else {
    console.log("Unexpected Error: ", error);
  }
}
```

---
## Related topics: 

- 

---
