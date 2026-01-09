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

## Build Amazon recommendation system using first thought principle.

### Solution 1: Using 1D array for database

- Grouping all items

![[1d-array-as-recommendation-system | 700]]

#### Problems with 1D array

- It's not Scalable (All tasks are manual).
- Boundaries are too rigid. For an example it won't recommend fruits with protein.
- Some extreme cases won't get covered. Like people buying diapars and beer cans together.

## Solution 2: Graph based solution

![[graph-based-solution-for-vector-database | 700]]

---
