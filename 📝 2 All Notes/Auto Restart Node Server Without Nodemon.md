---
tags:
  - nodejs
status: 🟩
---

2025-06-20        20:23

### 📘 `node --watch server.js`

The `--watch` flag in Node.js automatically **restarts your script** when **any files it depends on** are changed. This is useful during development to avoid restarting the server manually every time you make changes.

---

## ✅ Example Command:

```bash
node --watch server.js
```

This will:

- Run `server.js`
    
- Restart it automatically when any dependency file changes (like `server.js`, or any file it imports)

## Related topics: 

- [[fs.watch() method in node.js]]

## References

