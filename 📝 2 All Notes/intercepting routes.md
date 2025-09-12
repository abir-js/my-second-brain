---
tags: 
status:
---

2025-09-11        22:22

---
# What are Intercepting Routes?

- Intercepting routes let you show a page inside the current layout( like a modal or drawer ) instead of navigating away completely
- The URL still updates so it looks like you moved to another page
- If the user refreshes or share the link, they will see the full standalone page instead of the model.

## Why do we need intercepting routes?

- Better UX.
- Sharable URLs,
- Consistency

## Usages

- login/signup
- gallery
- side panel for settings
- quick previews

```
(.) --------> same level
(..) -------> one level above
(..)(..) ---> two level above
(...) ------> root level
```

---
