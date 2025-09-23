---
tags:
  - index
  - backend
---
# What is Redis?
- REDIS --> Remote Dictionary Server
- Open Source, in-memory, NoSQL Key-Value store
## Features
1. Caching - temporary storage of frequently access-able data
2. Fast DB operations
3. real time analytics due to exceptional speed and reliability
## Use cases
1. api response, db query results cache
2. session storage
3. real time analytics
4. message system: pub/sub
5. Leaderboards
6. Background Jobs

## docker code

```sh
docker run -d --name redis-stack -p 6379:6379 -p 8001:8001 redis/redis-stack:latest
```

```sh
docker exec -it redis-stack redis-cli
```


## Core data types in redis

1. string
2. list
3. hash
4. set
5. zset
6. streams
7. bitmaps
8. hyperlog
9. geospatial
10. timeseries

### Strings

#### 1. Set key value

```sh
set user:1 "name"
get user:1:name "ram"
```

#### 2. set expiry

```sh
set session:abc123 "user_data" ex 25
```

#### 3. increment

1. `incr`

```sh
set notification 90
incr notification
get notification
```

```sh
127.0.0.1:6379> set notification 90
OK
127.0.0.1:6379> incr notification
(integer) 91
127.0.0.1:6379> get notification
"91"
```

2. `incrby`

```sh
incrby notification 10
```

```sh
incrbyfloat notification 10
```


3. `nx`

```sh
127.0.0.1:6379> set likes:123 100 nx
OK
127.0.0.1:6379> set likes:123 100 nx
(nil)
127.0.0.1:6379> 
```

4. `xx` - only set if key exists

```sh
```

5. 

