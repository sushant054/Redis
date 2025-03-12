### 1. Redis commands for.. installation with docker
go to the website:
```
https://redis.io/docs/latest/operate/oss_and_stack/install/install-stack/docker/
```
 
```
docker run -d --name redis-stack -p [id] -p 8001:8001 redis/redis-stack:latest
```

 
### 2.  Then go to localhost:8001
   a) ping 
``` 
3. docker ps 
4. docker exec -it "past container id here" bash
```

then,

1. redis-cli 
```
Redis string
a. set name sushh!
b. get name
c. set msg:1 hey
d. set msg:1 hello nx   <----it gives (nil) because value already exists..for that we use [nx] cmd
```
5. [mget, mset] multiple get , multiple set  <-----eg. mset bike:1 "Deimon" bike:2 "vanth"

6. incr <-----increment 

single redis sting can be max. of 512 MB.
 
### Data Types:
```
https://redis.io/docs/latest/develop/data-types/
```
 
Use with node.js

1. npm i ioredis
2. in file ===> import {Redis} from 'ioredis' or const {Redis} = require ('ioredis')



## Lists
1. lpush <---push from left side 
eg. lpush messages hello
2. rpush 
3. llen messages  <----return length..
4. lpop, rpop   <---eg. lpop messages
5. lmove
6. ltrim

Blocking commands

1. blpop   <----blpop messages 10   <--sec.  and wait in blocking mode
2. lrange messages 0 -1  <----reads all messages til end..
3. del messages  <---delete messages

## Sets
1. sadd ip 1   <---here no duplicate..allowed..
2. sismember ip 1  <----if exists returns 1 otherwise 0
3. sinter <---gives common elements from sets..
4. scard <---returns the size of a set