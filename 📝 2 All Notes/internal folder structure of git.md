---
tags:
  - git
status: 🟩
---

2026-01-17        13:10

---
# What is Title?

```bash
cd .git
```

```sh
ls
```

## Files in .git

1. FETCH_HEAD      
2. description     
3. info
4. HEAD
	- stores current branch. eg-main
	- `git branch`
5. hooks           
6. objects
	- creates folders for each commit starting with first 2 letter of commit id. eg- **commit id: 2b9b0.....**
	1. 2b
		1. 9b0.....
		2. `cat 9b0....`
			- it stores changes, 
			- author, 
			- commit message
			- previous node address
	2. 05
	3. 52
	4. pack
	5. info
7. config          
8. index(file)
	1. `cat index`
		1. returns in zipped format
		2. stores which files to track.
9. refs
	1. heads
		1. main (branch name)
			- stores current commit's hash
	2. tags

### Outside of git folder - else it would search for .git folder inside .git

```sh
git cat-file -p <id>
```


---
