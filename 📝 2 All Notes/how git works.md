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

![[git-initialization | 1000]]

## See History - Git Log

```sh
git log
```

```sh
git log --oneline
```

- View the permanent, committed history of the repository.
- displays Commit SHAs, authors, dates, and commit messages.
## Git status

```sh
cat INDEX
```
- good way is ↓
```sh
git status
```

- view the current state of files in the working directory and staging area.
- displays Untracked files, modified files, and staged files (changes ready to be committed).
- Provides a snapshot of the current, local workspace, including staged and unstaged changes.
## See differences between two commits

```sh
git diff
```

```sh
git diff --oneline
```

## Remove bug

### 1. Git revert

```sh
git revert <id_that_contains_bug>
```

- creates a new commit that is negative of previous commit.
- history is maintained.

### 2. git reset

```sh
git reset --hard <previous_id_of_bug_commit>
```

- with hard, history gets deleted.
- without hard, later commit comes in staging area, you can recommit later.

![[remove-bug-using-git | 1000]]

## Gir revert vs git reset

![[git-reset-vs-git-revert | 1000]]


---
