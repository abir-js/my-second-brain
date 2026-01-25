---
tags: 
status:
---

2026-01-25        12:45

---
## ✅ `<figure>` Tag

- Used to wrap **self-contained content** like:
    
    - images
        
    - diagrams
        
    - charts
        
    - code snippets
        
    - illustrations
        
- It groups the media + its description together.
    

📌 Example:

```html
<figure>
  <img src="cat.jpg" alt="A cute cat">
</figure>
```

---

## ✅ `<figcaption>` Tag

- Used to give a **caption/description** for the content inside `<figure>`
    
- Must be inside `<figure>`
    
- Can be placed **at the top or bottom**
    

📌 Example:

```html
<figure>
  <img src="cat.jpg" alt="A cute cat">
  <figcaption>This is my pet cat.</figcaption>
</figure>
```

---

## ⭐ Why use them?

✅ Better **semantic HTML**  
✅ Improves **accessibility** (screen readers understand caption relation)  
✅ Cleaner structure for media + caption

---

### Example (Caption on Top)

```html
<figure>
  <figcaption>Figure 1: Cat Image</figcaption>
  <img src="cat.jpg" alt="A cute cat">
</figure>
```

---

