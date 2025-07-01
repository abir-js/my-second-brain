---
tags:
  - nodejs
status: 🟩
---

2025-06-21        12:18

# What is npm?

- npm is a popular package manager which comes bundled with Node.js.

- It is a CLI tool used to install, update, and remove external packages.

- You can also create your own package and publish it on [npmjs.com](https://www.npmjs.com/) registry.

- Do not confuse npm CLI with [npmjs.com](https://www.npmjs.com/) as it's a registry where most of the packages of Node.js are saved.

	- There are alternative Node.js package managers registry like **JSR**.

### Fun Facts:

-  npm should not written in capitalized form unless you have everything in capital.

- **npm does not stand for Node Package Manager** though many people prefer to it as that. It is a recursive acronymic abbreviation for "npm" is not an acronym.

## npm Commands:

1. Initialize project
```sh
npm i <package-name>
```

2. After installation you will find **node_modules** folder and **package.json**, **package-lock.json** file.
	
	- **node_modules:** stores all installed packages. 
	
	- **package-lock.json:** includes exact version of all packages that you install. It prevents breaking changes in newer versions of packages.

3. While importing, first Node.js checks for core modules, then files or folders, and at last looks inside node_modules.

### 4. npm install

```sh
npm i
```

### 5. npm list

- Because of symbols, the versions specified in package.json might not get installed.
- To see the exact versions of all packages installed in your project, use `-a` flag to see whole list.

```sh
npm list
```

### 6. npm view "package-name"

- To see details of a package that you installed including versions, license, author, and so on.

```sh
npm view express;
```

---
## Related topics: 

- [[Semantic Versioning]]

---
