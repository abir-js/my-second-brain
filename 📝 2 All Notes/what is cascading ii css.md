---
tags:
  - css
status: 🟩
---

2026-02-04        02:04

---
# What is Cascading?

CSS means cascading style sheet. When we change styles on an element, only that particular style value gets changed, else remains same.

```css
p {
	color: blue;
	background-color: "pink";
}
```

Then we change the color:
```css
p{
	color: red;
}
```

In the next step, color gets changed and the background color property also remains same. Else if it was replacing instead of cascading, then the background color will also get removed.

---
