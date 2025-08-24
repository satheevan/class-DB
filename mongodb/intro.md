# Introduction to mongodb

Mongodb is "document database".
You store record as documnet (think JSON objects)
inside collection within a database

# database -> collections (tables in MySQL) -> Documents (Rows in MySQL) -> Fields (colums in MySql)

-Every document has a unique "_id" (primary keys in MySql)
-Single-document operations are atomic all-or-nothing on the single document

### How does a React Equivalent of a Mongodb document look?

```js
const Student = {
    name:"Saravanan",
    age:30,
    city:"Bangalore",
    skills:["HTML","JS"]
    contact:{phone:"5434615"}
}
```

# Data Types

MongoDb stores data as VSON (Binary JSON). BSON is JSON-like but type and binary, so it's faster to parseand supports types JSON (eg: dates,dicimals,binary)

core data types:
    - Strings "SutendName"
    - Numbers :30
    - Boolean :active
    - Date:createdAt
    - Array:skills
    - Object:contact
    - Null / Regex (`https://regex101.com/`) / Binary : null / /patter eg:(`/Sa/i`) / `BinData(...)`


# What is an Object Id? `https://www.mongodb.com/docs/manual/reference/method/ObjectId/?msockid=2d9685db16bb6b950c5093d9171d6a0e`
An objectId is MongoDb default `_id` (one byte as 8 bits) type --a 12byte (12b x 8 bits -> 96 charaters)
Indentifer designed to be globally unique and increae over time .

# What an ObjectId look like?
ObjectId("5045dsfsdfsmnkdsfgldfkg")

## Structure of the 12 bites
    - 4 bytes : Unix timeStamp(seconds) -> `https://www.unixtimestamp.com/` gives you a creation time
    - 5 bytes : random value (per process/host)
    - 3 bytes - incrementing counter

```js
    const id = new ObjectId();
    id.getTimeStamp();
```

# Storage Engine

MongoDb's default engine is `WiredTiger`.
At out level today, know that it provides:
    - Durability
    - Compression ( effecient on disk)
    - Document level ConCurrency (good with many writers)
    - Predictable performance characteristics


mongodb port : mongodb://127.0.0.1.27017

# How to Install:

https://www.mongodb.com/try/download/community

shell : 
https://www.mongodb.com/products/tools/compass

# servies: stop/start

net start MongoDB

net stop MongoDB

# set mongodb
<!-- all documetn search binary tree -->

https://github.com/guvi-fsd/guvi-placement-practice/tree/main