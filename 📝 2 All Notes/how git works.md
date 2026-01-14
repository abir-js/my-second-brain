---
tags:
  - git
status: 🟩
---

2026-01-14        11:42

---
# How git works?

![[how-git-works]]

- We can track these changes in a special file called changes.txt file.
- The condition is user can't change these files.
- Means we don't need extra database or something.

## Start initialising Git.

- By default git does not tracks any file automatically.
- We need to initialise it using `git init` command

```sh
git init
```

![[git-init.png]]

## Start Tracking

```sh
git add <file-name>
```

## Save changes

```sh
git commit -m "message"
```

## See History - Git Log

```sh
git log
```

## See differences between two commits

```sh
git diff
```

```sh
git diff --oneline
```



---
