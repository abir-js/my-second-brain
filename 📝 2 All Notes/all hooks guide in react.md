---
tags:
  - react
status: 🟩
---

2025-07-21        21:12

---
## [Complete Guide to React Hooks](https://surajkumarjha.me/blog/react-hooks-guide#complete-guide-to-react-hooks)

## [1. useState Hook](https://surajkumarjha.me/blog/react-hooks-guide#1-usestate-hook)

### [Overview](https://surajkumarjha.me/blog/react-hooks-guide#overview)

`useState` is the most fundamental React hook that allows you to add state to functional components. It returns an array with two elements: the current state value and a function to update it.

### [Syntax](https://surajkumarjha.me/blog/react-hooks-guide#syntax)

```jsx
const [state, setState] = useState(initialValue);
```

### [Key Points](https://surajkumarjha.me/blog/react-hooks-guide#key-points)

- The initial value can be a primitive, object, or array
- State updates are asynchronous and may be batched
- When updating objects or arrays, you must create a new reference
- The setter function can accept a value or a callback function

### [Code Example](https://surajkumarjha.me/blog/react-hooks-guide#code-example)

```jsx
import React, { useState } from 'react';
function Counter() {  
	const [count, setCount] = useState(0);  
	const [user, setUser] = useState({ name: '', email: '' });  
	const increment = () => {    
		// Using callback function for state that depends on previous state    
		setCount(prevCount => prevCount + 1);  
	};  
	const updateUser = (field, value) => {    
		// Updating object state - must spread to create new object    
		setUser(prevUser => ({      
			...prevUser,      
			[field]: value    
		}));
	};  
	return (    
		<div>      
			<h2>Count: {count}</h2>      
			<button onClick={increment}>Increment</button>            
			<div>        
				<input
				placeholder="Name"    
				value={user.name}
				onChange={(e) => updateUser('name', e.target.value)}
				/>
				<input
				placeholder="Email"
				value={user.email}
				onChange={(e) => updateUser('email', e.target.value)}
				/>
				<p>User: {user.name} - {user.email}</p>
			</div>
		</div>  
	);
}
```

---

## [2. useEffect Hook](https://surajkumarjha.me/blog/react-hooks-guide#2-useeffect-hook)

### [Overview](https://surajkumarjha.me/blog/react-hooks-guide#overview-1)

`useEffect` handles side effects in functional components. It combines the functionality of `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount` from class components.

### [Syntax](https://surajkumarjha.me/blog/react-hooks-guide#syntax-1)

```
useEffect(() => {  // Effect logic  return () => {    // Cleanup function (optional)  };}, [dependencies]); // Dependency array (optional)
```

### [Key Points](https://surajkumarjha.me/blog/react-hooks-guide#key-points-1)

- Runs after every render by default
- Dependency array controls when effect runs
- Empty dependency array `[]` means run only once (on mount)
- No dependency array means run after every render
- Return function is for cleanup

### [Code Example](https://surajkumarjha.me/blog/react-hooks-guide#code-example-1)

```jsx
import React, { useState, useEffect } from 'react';
function UserProfile({ userId }) {  
	const [user, setUser] = useState(null);  
	const [loading, setLoading] = useState(true); 
	const [windowWidth, setWindowWidth] = useState(window.innerWidth);  
	// Effect with dependency - runs when userId changes  
	useEffect(() => {    
		const fetchUser = async () => {
			setLoading(true);      
			try {        
				// Simulating API call        
				const response = await fetch(`/api/users/${userId}`);        
				const userData = await response.json();        
				setUser(userData);      
			} catch (error) {        
				console.error('Error fetching user:', error);      
			} finally {        
				setLoading(false);      
			}    
		};    
		if (userId) {      
			fetchUser();    
		}  
	}, [userId]); 
	// Only run when userId changes  
	// Effect with cleanup - runs once on mount  
	useEffect(() => {    
	const handleResize = () => {      
		setWindowWidth(window.innerWidth);    
	};    
	// Add event listener    
	window.addEventListener('resize', handleResize);    
	// Cleanup function - removes event listener    
	return () => {      
		window.removeEventListener('resize', handleResize);    
	};  }, []); 
	// Empty dependency array - runs only once  
	// Effect without dependencies - runs after every render  
	useEffect(() => {    
		document.title = user ? `Profile: ${user.name}` : 'Loading...';  
	});  
	if (loading) return <div>Loading...</div>;  
	return (    
		<div>      
			<h2>User Profile</h2>      
			<p>Window Width: {windowWidth}px</p>      
			{user && (        
				<div>          
					<h3>{user.name}</h3>          
					<p>Email: {user.email}</p>        
				</div>      
			)}    
		</div>  
	);
}
```

---

## [3. useRef Hook](https://surajkumarjha.me/blog/react-hooks-guide#3-useref-hook)

### [Overview](https://surajkumarjha.me/blog/react-hooks-guide#overview-2)

`useRef` creates a mutable reference that persists across renders. It's commonly used for accessing DOM elements directly or storing mutable values that don't trigger re-renders.

### [Syntax](https://surajkumarjha.me/blog/react-hooks-guide#syntax-2)

```jsx
const ref = useRef(initialValue);
```

### [Key Points](https://surajkumarjha.me/blog/react-hooks-guide#key-points-2)

- `.current` property holds the actual value
- Changing `.current` doesn't trigger re-renders
- Perfect for DOM manipulation and storing previous values
- Useful for accessing child component methods

### [Code Example](https://surajkumarjha.me/blog/react-hooks-guide#code-example-2)

```jsx
import React, { useState, useRef, useEffect } from 'react';
function FocusInput() {  
	const [count, setCount] = useState(0);  
	const inputRef = useRef(null);  
	const previousCountRef = useRef();  
	const renderCountRef = useRef(0);  
	// Focus input on mount  useEffect(() => {    
	inputRef.current.focus();  }, []);  
	// Store previous count value  
	useEffect(() => {    
		previousCountRef.current = count;  
	});  
	// Track render count  
	renderCountRef.current += 1; 
	const handleFocus = () => {    
		// Direct DOM manipulation    
		inputRef.current.focus();    
		inputRef.current.select();  
	};  
	const handleClear = () => {    
		// Clear input value directly    
		inputRef.current.value = '';    
		inputRef.current.focus();  
	};  
	return (    
		<div>      
			<h2>useRef Example</h2>            
			<div>        
				<input          
				ref={inputRef}          
				placeholder="Type something..."          
				defaultValue="Hello World"        
				/>        
				<button onClick={handleFocus}>Focus & Select</button>
				<button onClick={handleClear}>Clear</button>      
			</div>      
			<div>        
				<p>Current count: {count}</p>        
				<p>Previous count: {previousCountRef.current}</p>        
				<p>Render count: {renderCountRef.current}</p>        
				<button onClick={() => setCount(count + 1)}>          
				Increment Count        
				</button>      
			</div>    
		</div>  );
}
```

---

## [4. useContext Hook](https://surajkumarjha.me/blog/react-hooks-guide#4-usecontext-hook)

### [Overview](https://surajkumarjha.me/blog/react-hooks-guide#overview-3)

`useContext` allows you to consume context values without wrapping components in Context.Consumer. It provides a clean way to access context data throughout your component tree.

### [Syntax](https://surajkumarjha.me/blog/react-hooks-guide#syntax-3)

```jsx
const contextValue = useContext(MyContext);
```

### [Key Points](https://surajkumarjha.me/blog/react-hooks-guide#key-points-3)

- Must be used within a Context Provider
- Automatically re-renders when context value changes
- Cleaner alternative to Context.Consumer
- Good for avoiding prop drilling

### [Code Example](https://surajkumarjha.me/blog/react-hooks-guide#code-example-3)

```
import React, { createContext, useContext, useState } from 'react';// Create contextsconst ThemeContext = createContext();const UserContext = createContext();// Theme Provider Componentfunction ThemeProvider({ children }) {  const [theme, setTheme] = useState('light');  const toggleTheme = () => {    setTheme(prevTheme => prevTheme === 'light' ? 'dark' : 'light');  };  return (    <ThemeContext.Provider value={{ theme, toggleTheme }}>      {children}    </ThemeContext.Provider>  );}// User Provider Componentfunction UserProvider({ children }) {  const [user, setUser] = useState({ name: 'John Doe', role: 'admin' });  const updateUser = (updates) => {    setUser(prevUser => ({ ...prevUser, ...updates }));  };  return (    <UserContext.Provider value={{ user, updateUser }}>      {children}    </UserContext.Provider>  );}// Component using multiple contextsfunction Header() {  const { theme, toggleTheme } = useContext(ThemeContext);  const { user } = useContext(UserContext);  return (    <header style={{      backgroundColor: theme === 'light' ? '#fff' : '#333',      color: theme === 'light' ? '#000' : '#fff',      padding: '1rem'    }}>      <h1>Welcome, {user.name}!</h1>      <button onClick={toggleTheme}>        Switch to {theme === 'light' ? 'dark' : 'light'} theme      </button>    </header>  );}// Nested component accessing contextfunction UserProfile() {  const { user, updateUser } = useContext(UserContext);  const { theme } = useContext(ThemeContext);  return (    <div style={{      backgroundColor: theme === 'light' ? '#f5f5f5' : '#444',      color: theme === 'light' ? '#000' : '#fff',      padding: '1rem',      margin: '1rem'    }}>      <h2>User Profile</h2>      <p>Name: {user.name}</p>      <p>Role: {user.role}</p>      <button onClick={() => updateUser({ name: 'Jane Smith' })}>        Change Name      </button>    </div>  );}// Main App Componentfunction App() {  return (    <ThemeProvider>      <UserProvider>        <Header />        <UserProfile />      </UserProvider>    </ThemeProvider>  );}
```

---

## [5. useMemo Hook](https://surajkumarjha.me/blog/react-hooks-guide#5-usememo-hook)

### [Overview](https://surajkumarjha.me/blog/react-hooks-guide#overview-4)

`useMemo` memoizes the result of a computation and only recalculates when dependencies change. It's used for performance optimization to avoid expensive calculations on every render.

### [Syntax](https://surajkumarjha.me/blog/react-hooks-guide#syntax-4)

```
const memoizedValue = useMemo(() => {  return expensiveCalculation();}, [dependencies]);
```

### [Key Points](https://surajkumarjha.me/blog/react-hooks-guide#key-points-4)

- Only recalculates when dependencies change
- Helps prevent expensive calculations on every render
- Returns the memoized value, not a function
- Don't overuse - has its own overhead

### [Code Example](https://surajkumarjha.me/blog/react-hooks-guide#code-example-4)

```
import React, { useState, useMemo } from 'react';function ExpensiveCalculationComponent() {  const [count, setCount] = useState(0);  const [todos, setTodos] = useState([]);  const [filter, setFilter] = useState('all');  // Expensive calculation that we want to memoize  const expensiveValue = useMemo(() => {    console.log('Calculating expensive value...');    let result = 0;    for (let i = 0; i < 1000000; i++) {      result += i * count;    }    return result;  }, [count]); // Only recalculate when count changes  // Memoized filtered todos  const filteredTodos = useMemo(() => {    console.log('Filtering todos...');    switch (filter) {      case 'completed':        return todos.filter(todo => todo.completed);      case 'active':        return todos.filter(todo => !todo.completed);      default:        return todos;    }  }, [todos, filter]); // Recalculate when todos or filter changes  // Memoized statistics  const todoStats = useMemo(() => {    console.log('Calculating todo statistics...');    return {      total: todos.length,      completed: todos.filter(todo => todo.completed).length,      active: todos.filter(todo => !todo.completed).length    };  }, [todos]);  const addTodo = () => {    setTodos(prevTodos => [      ...prevTodos,      {        id: Date.now(),        text: `Todo ${prevTodos.length + 1}`,        completed: Math.random() > 0.5      }    ]);  };  const toggleTodo = (id) => {    setTodos(prevTodos =>      prevTodos.map(todo =>        todo.id === id ? { ...todo, completed: !todo.completed } : todo      )    );  };  return (    <div>      <h2>useMemo Example</h2>            <div>        <p>Count: {count}</p>        <p>Expensive Calculation Result: {expensiveValue}</p>        <button onClick={() => setCount(count + 1)}>          Increment Count        </button>      </div>      <div>        <h3>Todo Statistics</h3>        <p>Total: {todoStats.total}</p>        <p>Completed: {todoStats.completed}</p>        <p>Active: {todoStats.active}</p>      </div>      <div>        <button onClick={addTodo}>Add Todo</button>        <select value={filter} onChange={(e) => setFilter(e.target.value)}>          <option value="all">All</option>          <option value="active">Active</option>          <option value="completed">Completed</option>        </select>      </div>      <div>        <h3>Filtered Todos ({filteredTodos.length})</h3>        {filteredTodos.map(todo => (          <div key={todo.id}>            <label>              <input                type="checkbox"                checked={todo.completed}                onChange={() => toggleTodo(todo.id)}              />              {todo.text}            </label>          </div>        ))}      </div>    </div>  );}
```

---

## [6. useCallback Hook](https://surajkumarjha.me/blog/react-hooks-guide#6-usecallback-hook)

### [Overview](https://surajkumarjha.me/blog/react-hooks-guide#overview-5)

`useCallback` memoizes a function and only creates a new function when dependencies change. It's primarily used to prevent unnecessary re-renders of child components that depend on callback functions.

### [Syntax](https://surajkumarjha.me/blog/react-hooks-guide#syntax-5)

```
const memoizedCallback = useCallback(() => {  // Function logic}, [dependencies]);
```

### [Key Points](https://surajkumarjha.me/blog/react-hooks-guide#key-points-5)

- Returns a memoized function, not the result of the function
- Prevents child component re-renders when passed as props
- Only creates new function when dependencies change
- Most useful with React.memo components

### [Code Example](https://surajkumarjha.me/blog/react-hooks-guide#code-example-5)

```
import React, { useState, useCallback, memo } from 'react';// Child component wrapped with React.memo for optimizationconst TodoItem = memo(({ todo, onToggle, onDelete }) => {  console.log(`Rendering TodoItem: ${todo.text}`);    return (    <div style={{       padding: '0.5rem',       margin: '0.25rem 0',      backgroundColor: todo.completed ? '#e8f5e8' : '#fff3cd',      border: '1px solid #ccc'    }}>      <label>        <input          type="checkbox"          checked={todo.completed}          onChange={() => onToggle(todo.id)}        />        <span style={{           textDecoration: todo.completed ? 'line-through' : 'none',          marginLeft: '0.5rem'        }}>          {todo.text}        </span>      </label>      <button         onClick={() => onDelete(todo.id)}        style={{ marginLeft: '1rem', color: 'red' }}      >        Delete      </button>    </div>  );});// Another memoized child componentconst AddTodoForm = memo(({ onAddTodo }) => {  console.log('Rendering AddTodoForm');  const [text, setText] = useState('');  const handleSubmit = (e) => {    e.preventDefault();    if (text.trim()) {      onAddTodo(text.trim());      setText('');    }  };  return (    <form onSubmit={handleSubmit} style={{ marginBottom: '1rem' }}>      <input        type="text"        value={text}        onChange={(e) => setText(e.target.value)}        placeholder="Enter todo text..."        style={{ marginRight: '0.5rem', padding: '0.25rem' }}      />      <button type="submit">Add Todo</button>    </form>  );});// Main component using useCallbackfunction TodoApp() {  const [todos, setTodos] = useState([]);  const [filter, setFilter] = useState('all');  // Memoized callback functions  const handleToggleTodo = useCallback((id) => {    console.log('Toggle todo called');    setTodos(prevTodos =>      prevTodos.map(todo =>        todo.id === id ? { ...todo, completed: !todo.completed } : todo      )    );  }, []); // No dependencies - function never changes  const handleDeleteTodo = useCallback((id) => {    console.log('Delete todo called');    setTodos(prevTodos => prevTodos.filter(todo => todo.id !== id));  }, []); // No dependencies - function never changes  const handleAddTodo = useCallback((text) => {    console.log('Add todo called');    const newTodo = {      id: Date.now(),      text,      completed: false    };    setTodos(prevTodos => [...prevTodos, newTodo]);  }, []); // No dependencies - function never changes  // This callback depends on filter, so it will recreate when filter changes  const getFilteredTodos = useCallback(() => {    switch (filter) {      case 'completed':        return todos.filter(todo => todo.completed);      case 'active':        return todos.filter(todo => !todo.completed);      default:        return todos;    }  }, [todos, filter]); // Recreates when todos or filter changes  const filteredTodos = getFilteredTodos();  return (    <div style={{ padding: '1rem' }}>      <h2>useCallback Todo App</h2>            <AddTodoForm onAddTodo={handleAddTodo} />            <div style={{ marginBottom: '1rem' }}>        <label>          Filter:           <select             value={filter}             onChange={(e) => setFilter(e.target.value)}            style={{ marginLeft: '0.5rem' }}          >            <option value="all">All ({todos.length})</option>            <option value="active">              Active ({todos.filter(t => !t.completed).length})            </option>            <option value="completed">              Completed ({todos.filter(t => t.completed).length})            </option>          </select>        </label>      </div>      <div>        {filteredTodos.length === 0 ? (          <p>No todos to display</p>        ) : (          filteredTodos.map(todo => (            <TodoItem              key={todo.id}              todo={todo}              onToggle={handleToggleTodo}              onDelete={handleDeleteTodo}            />          ))        )}      </div>    </div>  );}
```

## [Hook Best Practices](https://surajkumarjha.me/blog/react-hooks-guide#hook-best-practices)

### [1. Rules of Hooks](https://surajkumarjha.me/blog/react-hooks-guide#1-rules-of-hooks)

- Only call hooks at the top level of functions
- Don't call hooks inside loops, conditions, or nested functions
- Only call hooks from React functions or custom hooks

### [2. Performance Tips](https://surajkumarjha.me/blog/react-hooks-guide#2-performance-tips)

- Use `useMemo` and `useCallback` sparingly - they have overhead
- Consider React.memo for expensive child components
- Profile before optimizing

### [3. Common Patterns](https://surajkumarjha.me/blog/react-hooks-guide#3-common-patterns)

- Custom hooks for reusable logic
- Combine multiple hooks for complex state management
- Use useReducer for complex state transitions

### [4. Testing Considerations](https://surajkumarjha.me/blog/react-hooks-guide#4-testing-considerations)

- Test hook behavior, not implementation
- Use React Testing Library for hook testing
- Consider creating custom hooks for complex logic

This guide covers the six most commonly used React hooks with practical examples that demonstrate real-world usage patterns and best practices.

---
