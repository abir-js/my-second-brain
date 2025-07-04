---
tags:
  - nodejs
status: 🟩
---

2025-06-28        17:53

# What are streams and buffers?

![[streams-nodejs.png]]

- Let's imagine a client has 8 GB RAM, and server has 16 GB RAM.

- If a client wants to upload a 2TB file to the server, then what it can do is give whole 2TB file to server, Then server can store it in disk. But is that possible?

	- Its not possible because client first take whole 2TB file in their RAM, then upload it to the server, then server should initially store whole 2TB file in RAM, then store in disk.
	
- Neither the client has 2 TB RAM, nor the server can handle it. In that case, we have to split the file into chunks and server should take file in chunks and write into disk at the same time.

---
## Streams

- Streams in Node.js are a **way to handle continuous flow of data**.
- They enable reading or writing data piece by piece instead of loading the entire data into memory.
- There are four types of streams - 
  1. Writable
  2. Readable
  3. Duplex
  4. Transform
  
- All streams are instances of [[Event Emitter in Node.js | EventEmitter]].

| Stream Type   | Description                                             | Example                  |
| ------------- | ------------------------------------------------------- | ------------------------ |
| **Readable**  | Can read data from it                                   | `fs.createReadStream()`  |
| **Writable**  | Can write data to it                                    | `fs.createWriteStream()` |
| **Duplex**    | Can read and write (both directions)                    | `net.Socket`             |
| **Transform** | Duplex + modify data during read/write (i.e. transform) | `zlib.createGzip()`      |


## Buffer

- A buffer in Node.js is a **temporary storage area for binary data**.
- Buffer works as chunks of data, enabling efficient data manipulation in streams.
- It helps decrease memory consumption in web server.


---
## Related topics: 

- [node-streams](https://nodejs.org/api/stream.html)

---
