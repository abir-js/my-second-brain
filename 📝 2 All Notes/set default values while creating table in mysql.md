---
tags:
  - mysql
status:
---

2025-07-19        12:55

## Set default value in table

```mysql
CREATE TABLE games(
    name VARCHAR(50) DEFAULT 'Anonymous',
    release_year INT DEFAULT 2025,
    ratings INT
);
```

