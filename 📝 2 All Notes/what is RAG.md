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
- it will store its vector and its meta data. it helps to get original sentence from vector.

onion --> vector, onion

```json
{
  "id": "hash",  // for indexing and exact searching
  "vector": "[0.98, 0.23, 0.45]",  
  "meta_data": {
	  "product_name": "running shoes",
	  "price": "89.99",
  }
}
```

- We use these id to exactly search (not semantic search) for any vector to identify, update or delete it.

---
## What is RAG?

- Retrieval Augmented Generation
### Problem:

- suppose you have your own dsa notes and you want to revisit binary search from your notes.
	- one option is that you can get general answers from any LLM.
	- but to get answer from your own notes, you have to give your notes as a context.
	- but sending that much info is token consuming and costly.

### Solution

- put all these notes in vector database
- divide all notes into multiple chunks.
- create vector for all chunks.

![[rag | 1000]]



---
