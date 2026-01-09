---
tags:
  - genai
status: 🟩
---

2026-01-09        15:00

---
# How recommendation system works?

- You search for web development full course and get multiple answers. Even some keywords doesn't matches.
- There are multiple playlists for web development.
- How is it suggesting top 5.

eg -  **You added potato in card and got onion in recommendation**

---
## Build Amazon recommendation system using first thought principle.

### Solution 1: Using 1D array for database

- Grouping all items within same category

![[1d-array-as-recommendation-system | 700]]

#### Problems with 1D array

- It's not Scalable (All tasks are manual).
- Boundaries are too rigid. For an example it won't recommend fruits with protein.
- Some extreme cases won't get covered. Like people buying diapars and beer cans together.

---
## Solution 2: Graph based solution

![[graph-based-solution-for-vector-database | 700]]

### Problems

1. size of matrix is N x N
2. To recommend best element, it would take time for sorting.
3. "**Cold Start problem**" - at first, we won't be able to recommend.
4. If new product comes of same category, you won't be able to recommend other products with it.

---

## Solution 3: 

We will assign numbers to each item and recommend based on its neighbour items.

```c
[apple, banana,....pant, protein, creatine,.....]
```

### Problems

1. **"The Single meaning problem"**
2. **"The boundary problem"**
3. **"The Insertion problem"**

---

## Solution 4: Vector

Netflix movie recommendation system

1. Dhaamal
2. Hera Pheri

![[vector | 700]]

---

