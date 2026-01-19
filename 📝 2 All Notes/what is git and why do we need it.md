---
tags:
  - git
status: 🟩
---

2026-01-14        11:35

---
## Why Git?

- As a coder we write code. There problem comes when out code grows, complexity increases, line of code.
- Managing it becomes difficult.
	- backup
		- backup can be easily done using any drive like Mega etc.
	- tracking
		- for example when we use google docs, it maintains history.
		- who changes, when changes, what get changed
			- we can easily go back to pervious versions.
		- So we also need tracking in code.
- for multiple developers collaboration
	- history management - manage history of local code
		- VCS(version control system)

### 1. Pendrive approach

- Suppose we are creating a project and it grows overtime.
- Taking help from another person for a feature.
- Use a pen-drive.
- Give them pendrive, they push their code and gives you back.
- They again takes pendrive and updates the code.
- You don't know which part got updated. **No tracking**

#### Problems: 

1. Syncing problem, at a time single developer can work.
2. No collaboration.
3. If someone changes their local code, 2 different repo exists.
4. with more difficult it becomes more confusing.

---
### 2. Code tracking system 

- Its a software.
- Install it on any device maybe on pendrive and whenever someone changes it stores who is changing and what is he changing.

#### Problem

- Still no collaboration, multiple people cant change at a same time.

---

### 3. A central code tracker server

- Now instead of pendrive, we will treat the server as the single source of truth.
- We are installing our code tracking system on our server
- Everyone can work on same project at a same time.

---
### **Summary**

- Here the code tracking software is Git and the server is GitHub.
- Github is the server which hosts Git
- There are many servers like BitBucket, GitLab, GitTea.
- You can buy a server and install git in it.

---
