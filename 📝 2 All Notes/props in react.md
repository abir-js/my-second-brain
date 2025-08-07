---
tags:
  - react
status: 🟩
---

2025-07-15        14:01

# What are Props in React?

- React props are like function arguments in JavaScript and attributes in HTML.
- To send props into a component, use the same syntax as HTML attributes:



```jsx
<Product title="phone" price="30k"/>
```

```jsx
<Product title="laptop" price={60000}/>
```

```jsx
export default function Product ({title, price}){
	return(
		<div>
			<h4>{title}</h4>
			<p>{product}</p>
		</div>
	)
}
```

---
## Passing arrays, objects to props

```jsx
// Parent Component
function ProductTab() {
	let options = ["hi-tech", "durable", "fast"];
	let options2 = { a: "hi-tech", b: "durable", c: "fast" };
	return (
	<>
		<Product
			title="phone"
			price={30000}
			features={options}
			features2={options2}
		/>
		<Product title="laptop" price={40000}
		<Product title="pen" price={1} />
	</>
);
```

```jsx
// Child Component
import "./Product.css";

function Product({title, price, features, features2}){
	return (
		<div className="Product">
			<h3>{title}</h3>
			<h5>Price : {price}</h5>
			<p>{features}</p>
			<p>{features2}</p>
		</div>
	);
}

export default Product;
```
