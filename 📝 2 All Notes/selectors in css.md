---
tags:
  - css
status: 🟩
---

2026-02-03        02:22

---
# What is Title?

Selectors are used to select an element and give it style.

## DOM

![[dom-for-css | 1000]]

## 1. Universal Selectors

- remove browser default css

```css
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
```

## 2. Type selector

```css
p {
	
}
```

## 3. Id Selector

```css
#login-btn {

}
```

## 4. Class Selector

```css
.container {

}
```

## 5. Attribute Selector

```css
input[type="text"] {
	border: 2px solid black;
}
```

## 6. Descendant Selectors

```html
<article>
	<p>Paragraph</p>
</article>
```

```css
article p {

}
```

## 7. Child Selector

```html
<div>
	<p>This gets selected</p>
	<div>
		<p>This does not gets selected</p>
	</div>
	<p>This gets selected</p>
</div>
```

```css
div > p {
	color: blue;
}
```

## 8. adjacent Sibling Selector

```css
h1 + p {

}
```

---
