---
tags:
  - react
status: 🟩
---

2025-07-16        13:07

# What are hooks?

- React Hooks are special JavaScript functions introduced in React 16.8 that allow developers to use state and other React features within functional components. Prior to Hooks, these capabilities were primarily available only in class components.

Key aspects of React Hooks include:

- **Enabling State Management in Functional Components:**
    
    Hooks like `useState` allow functional components to manage and update their own internal state, which was previously a core feature of class components.
    
- **Handling Side Effects:**
    
    Hooks such as `useEffect` provide a way to perform side effects (e.g., data fetching, DOM manipulation, subscriptions) in functional components, similar to lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount` in class components.
    

- **Reusability of Logic:**
    
    Hooks facilitate the creation of custom hooks, which are functions that encapsulate reusable stateful logic and can be shared across multiple components, promoting code reusability and reducing boilerplate.
    

- **Simplified Code Structure:**
    
    By allowing state and side effects within functions, Hooks often lead to more concise, readable, and organized code compared to class components, especially for complex logic.
    

- **Functional Approach:**
    
    Hooks align with a more functional programming paradigm in React, making it easier to reason about component behavior and manage complexity.
    

Examples of commonly used built-in React Hooks include `useState`, `useEffect`, `useContext`, `useReducer`, `useCallback`, `useMemo`, and `useRef`.

---
