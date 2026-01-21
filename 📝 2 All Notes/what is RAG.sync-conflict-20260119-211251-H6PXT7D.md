---
tags:
  - genai
status: 🟩
---

2026-01-14        21:17

---
## What actually gets stored in vector database?

- Vector and its meta data 
- For example you want to store "My name is Abir Bhattacharjee".
- it will store its vector and its meta data.

```json
{
  "id": "hash",
  "source": "blog_post",
  "author": "Abir",
  "created_at": "2025-01-14",
  "doc_id": "post_42",
  "chunk_index": 3
}
```

- We use these id to exactly search (not semantic search) for any vector to identify, update or delete it.

---
## What is RAG?

- Retrieval Augmented Generation

For creating any personalised chatbot for DSA instructor, we need to five it full context of chat. 

### problem with this method

- more tokens needed to send whole chat.

![[Excalidraw/rag| 1000]]

---
