---
tags:
  - javascript
  - js-interview-questions
status: 🟩
---

2025-06-30        21:16


# In browser

```js
console.log(this) // Window
```

```js
"use strict";
console.log(this) // Window
```

## This keyword in function

```js
function fn(){
	console.log(this) // Window
}
```

```js
"use strict";
function fn(){
	console.log(this) // undefined
}
```

### This keyword substitution

- In non-strict mode, if value of this is null or undefined, then the value gets replaced by Window object
- In strict mode - value stays undefined, or actual value

## This keyword in object

==function as a property of an object - Method==

```js
const person1 = {
	
}
```

---
## This in arrow function

### lexically enclosed context

- arrow functions ka khudka this nhi hota
- jahapar apne arrow function ko banaya hai, uska level pe execute hota hai

```js
const hello = () ={
	console.log(this) // window
}
```

```js
"use strict";
const hello = () ={
	console.log(this) // window
}
```

- both of these gets executes as
```js
console.log(this) // Window
```

#### Example



## This in DOM

---
## In node.js

```js
console.log(this) // undefined
```

---
## Related topics: 

- 

---
