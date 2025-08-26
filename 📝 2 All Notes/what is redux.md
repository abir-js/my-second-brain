---
tags:
  - react
  - redux
status: 🟩
---

2025-08-21        23:59

---
# What is Redux?

- State management library for JS Apps
- Redux is built for larger, more complex applications.
- **Redux Toolkit** is the official recommendation of writing redux code.
---

## Understanding Terms

### Store : 
A centralized store holds the whole state tree of your application.

### Reducers:
Functions that take the current state and an action as an arguments, and return a new state result. In other words, (state, action) => newState.

### Action:
it is a plain javaScript object that has a type field. (like events)

### Slice 
Collections of Redux reducer logic and actions for  a single feature in your app typically together in a single file.