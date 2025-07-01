---
tags:
  - nodejs
status: 🟩
---

2025-06-19        02:03

# Why double \ instead of single \ in windows?

![[windows-path-problem.png]]

## 🔹 JavaScript strings escape backslashes

In JavaScript, **backslash is an escape character** (used for `\n`, `\t`, etc.).  
So, to represent a single backslash in a string, you **need to escape it** with another backslash.

### Example:


```js
const path = require('path'); 
const filePath = path.join('C:', 'Users', 'Abir', 'file.txt');  
console.log(filePath); // C:\Users\Abir\file.txt
```

If you inspect the string or log it in a **formatted** way, it may look like:

``` bash
'C:\\Users\\Abir\\file.txt'
```

That doesn’t mean the path has extra backslashes — it's just how JavaScript **displays** it as a string literal. The actual value still has single backslashes.

## Related topics: 

- 

## References

