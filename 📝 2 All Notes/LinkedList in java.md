---
tags:
  - java
  - dsa
  - linkedlist
status: 🟩
---

2025-08-23        22:49

---
# What is LinkedList?



## Singly LinkedList

![[linkedlist]]

1. **Create/Insert**
	1. At start
	2. middle/position
	3. at last
2. **Deletion**
	1. first
	2. middle
	3. end

```java
class Node {
	int data;
	Node next;
	
	// Constructor
	Node(int x){
		data = x;   
		next = null 
	}
}

class linkedlist{
	main(){
		Node temp = new Node(10);
	}
}
//         ---------------------
//         |    10   |   null   |
//         ---------------------
```

---
