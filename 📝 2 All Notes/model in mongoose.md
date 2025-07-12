---
tags:
  - backend
  - "#mongoose"
  - cohort
status: 🟩
---

2025-07-05        22:44

### 🏗️ `mongoose.model()` — What It Does in Mongoose

`mongoose.model()` is used to **create a model** based on a **schema**.  
A **model** is a class with which you construct documents for a specific **collection** in MongoDB.

---

### ✅ Syntax

```js
const ModelName = mongoose.model('ModelName', schema);
```

- `'ModelName'`: The **name** of the model (Mongoose will automatically convert it to lowercase and pluralize it to form the collection name).
    
- `schema`: The **Schema object** that defines the structure of the documents.
    

---

### 🔍 Example

```js
import mongoose from 'mongoose';

const userSchema = new mongoose.Schema({
  name: String,
  email: String,
});

const User = mongoose.model('User', userSchema);
```

➡️ Mongoose will create a **`users`** collection (lowercase + plural) in MongoDB and use the `userSchema` structure for documents.

---

### 📄 Using the Model

```js
// Create a new user document
const newUser = new User({
  name: 'Abir',
  email: 'abir@example.com'
});

// Save to DB
await newUser.save();

// Find users
const users = await User.find();

// Delete user
await User.deleteOne({ email: 'abir@example.com' });
```

---

### ⚠️ Notes

- If you call `mongoose.model('User', userSchema)` **more than once**, Mongoose will throw an **overwrite model error**. To avoid this:
    

```js
const User = mongoose.models.User || mongoose.model('User', userSchema);
```

---

Let me know if you want to explore:

- how to connect Mongoose to MongoDB
    
- how to define schema methods/statics
    
- or how to populate referenced data (`.populate()`)

---
## Related topics: 

- 

---
