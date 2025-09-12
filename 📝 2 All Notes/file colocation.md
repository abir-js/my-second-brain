---
tags:
  - nextjs
status: 🟩
---

2025-09-10        22:08

---
# File Colocation in Next JS

In **Next.js**, _file colocation_ means keeping the files that belong to a component, page, or feature **close to where they are used**, instead of spreading them across a global `components/`, `styles/`, or `utils/` folder.

👉 The goal is **better organization, modularity, and maintainability**.

---

### 🔹 Example without colocation (traditional way)

```
/components
   └── Card.tsx
/styles
   └── card.module.css
/utils
   └── formatDate.ts
/pages
   └── index.tsx
```

Here, `Card`’s logic, styles, and helpers are spread across multiple folders.

---

### 🔹 Example with file colocation

```
/app
   /card
      ├── Card.tsx
      ├── card.module.css
      └── utils.ts
   /page.tsx
```

- The `Card` component, its CSS, and helper functions live together in `/card`.
    
- `page.tsx` just imports from `./card/Card`.
    

---

### 🔹 Colocation in the **App Router**

With the Next.js App Router (`/app` directory), colocation is natural because:

- You can place a **page**, **loading**, **error**, **layout**, **styles**, and **components** together in a route folder.
    

Example:

```
/app
   /dashboard
      ├── page.tsx         // Dashboard page
      ├── layout.tsx       // Dashboard layout
      ├── loading.tsx      // Suspense loading state
      ├── error.tsx        // Error boundary
      ├── DashboardChart.tsx
      ├── dashboard.module.css
```

---

### 🔹 Benefits

- **Encapsulation**: Each feature manages its own code, reducing coupling.
    
- **Scalability**: Easier to onboard new devs—everything related is in one place.
    
- **Cleaner imports**: You don’t need long relative paths across multiple folders.
    

---

✅ In short: _File colocation in Next.js means keeping related files (components, styles, utils, tests, etc.) in the same folder, often near the page or feature that uses them—especially natural in the App Router structure._

---
