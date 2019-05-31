# 12 - Redis

## Introduction to Databases

- Relational Databases. `SQL`

- Non relation Databases. `MongoDB Query Language`

Build application without defined a schema.
Document Orientend.


## Redis commands.

[documentation](https://redis.io/commands/)
 
```shell
SET name "smgueye.io"
GET name

EXISTS name
DEL name
...
```

## Redis data types.
```
MSET a 1 b 5
OK
//=> a:1, b:5
GET a
GET b
MGET a b
```

## Redis Hashes
```
HMSET user id 45 name Momo
HGET user id
HGETALL user
```

## Redis List
Very fast for insertion because implementing linked list.

```
LPUSH ourlist 10 // Left push
RPUSH ourlist "hello" // right push
LRANGE 0 1
RDROP
LTRIM

```

## Redis Set & Stored Sets

- SADD  {key} {element(s)}
```
SADD ourset 1 2 3 4 5
```

- SMEMBERS {key}
```
SMEMBERS oursets
```

- Is member: SISMEMBER {key} {value}
```
SISMEMBER ourset 20
```

- Sorted Sets: ZADD {key} {number} {value}
```
ZADD team 50 "Wizards"
ZADD team 40 "Calvaliers"
ZrRANGE tean 0 1
// => 1. Calvaliers 2. Wizards because 40 < 50

ZRANK tean "Wizard"
// => 2
```