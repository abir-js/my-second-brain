---
tags:
  - nodejs
status: 🟩
---

2025-06-20        11:45

# Create a program using Node.js EventEmitter that?

### 1. Listens for multiple of user events (e.g. login, logout, and profile update).
### 2. Tracks how many times each event is emitted.
### 3. Logs a summary of all event occurrence when a special event is triggered.

```js
/* Requirements
1.  Create at least four events (e.g. user-login, user-logout, user-purchase, profile-update).

 2. Emit these events multiple times with diferent arguments (e.g. username, item purchased).
 
 3. Track and store count of each event Type.
 
 4. Define a summary event that logs a report of how many times eah event was triggered.
*/

const EventEmitter = require("events");
const Emitter = new EventEmitter();

const eventCount = {
  userLogin: 0,
  userLogout: 0,
  userPurchase: 0,
  profileUpdate: 0,
};

Emitter.on("userLogin", (user) => {
  eventCount["userLogin"]++;
  console.log(`${user.username} just logged in`);
});

Emitter.on("userLogout", (user) => {
  eventCount["userLogout"]++;
  console.log(`${user.username} just logged out`);
});

Emitter.on("userPurchase", (user) => {
  eventCount["userPurchase"]++;
  console.log(`${user.username} just purchased ${user.item}`);
});

Emitter.on("profileUpdate", (user) => {
  eventCount["profileUpdate"]++;
  console.log(`${user.username} just updated profile`);
});

Emitter.on("eventCountDetails", (userActivity) => {
  console.log(userActivity);
});

Emitter.emit("userLogin", { username: "Abir" });
Emitter.emit("userLogout", { username: "Abir" });
Emitter.emit("userLogin", { username: "Ram" });
Emitter.emit("profileUpdate", { username: "Ram" });
Emitter.emit("userPurchase", { username: "Ram", item: "Laptop" });
Emitter.emit("userLogout", { username: "Ram" });

Emitter.emit("eventCountDetails", eventCount);
```

## Related topics: 

- 

## References

