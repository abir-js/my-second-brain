---
tags:
  - git
status: 🟩
---

2026-01-17        13:10

---
# How git works?

- On your local machine you have git installed.
- there are multiple projects on your device.
- by default git does not tracks all files.

```sh
git init
```

- it initializes a .git folder
- `U` - untracked files

```sh
git add file_name
```

```sh
git add .
```

- comes in staging area
- git starts tracking
- `A` - index tracking

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
		1. inside 2b, `ls`
			1. 9b0.....
			2. `cat 9b0....`
				1. returns in compressed format
			3. `git cat-file -p 9b0...`
				- `-p` for print, `-t` for type
				- it stores changes, 
				- author, 
				- commit message
				- previous node address
			4. `git cat-file -p 9b0...`
	2. 05
	3. 52
	4. pack
	5. info
7. config          
8. index(file)
	1. `cat index`
		1. returns in zipped compressed format
		2. stores which files to track.
		3. `git status` - works same
9. refs
	1. heads
		1. main (branch name)
			- stores current commit's hash
	2. tags

### Outside of git folder - else it would search for .git folder inside .git

```sh
git cat-file -p <id>
```

## Commit

```sh
git commit -m "message"
```

- its like checkpoint
- every comment has its hashed id

### Show

```sh
git log
```

- commit id, brach name
- author
- date and time
- commit message



---
