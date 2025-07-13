---
tags:
  - react
status: 🟩
---

2025-07-13        16:14

# What is Title?

```js
<script
	crossorigin
	src="https://unpkg.com/react@18/umd/react.development.js"
></script>

<script
	crossorigin
	src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"
></script>
```

```html
<!--Index.html-->

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <h1>Hello</h1>
    <div id="root"></div>
    
    <script
      crossorigin
      src="https://unpkg.com/react@18/umd/react.development.js"
    ></script>
    <script
      crossorigin
      src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"
    ></script>
    >
    <script src="./script.js"></script>
  </body>
</html>
```

```js
// script.js
const H1 = React.createElement("h1", {classname: "heading"}, "deading");
const root = ReactDOM.createRoot(document.getElementById("root));
root.render(H1);
```


---
## Related topics: 

- 

---
