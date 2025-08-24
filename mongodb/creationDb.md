# Creating a database, collection & documents:

# pick or create Database

```js
use namedb
```

# Create Collection

```js
db.createCollection("students");
```

# Insert Collection:

# single document

```js
    // its object like bson
    db.students.insertOne({
        name:"saravanan",
        email:"saravanan@gamil.com",
        age:25,
        city:"Bangalore",
        Skills:["React","JS"],
        contact:{phone:"5615465165"},
        createdAt:new Date(),
    })
```

# Many document

```js
    // its object like bson
    db.students.insertMany(
        [
        {
        name:"user0",
        email:"user0@gamil.com",
        age:25,
        city:"Bangalore",
        Skills:["React","JS"],
        contact:{phone:"5615465165"},
        createdAt:new Date(),
    },
      {
        name:"user1",
        email:"user1@gamil.com",
        age:25,
        city:"Bangalore",
        Skills:["React","JS"],
        contact:{phone:"5615465165"},
        createdAt:new Date(),
    },
      {
        name:"user2",
        email:"user2@gamil.com",
        age:25,
        city:"Bangalore",
        Skills:["React","JS"],
        contact:{phone:"5615465165"},
        createdAt:new Date(),
    }
    ],)
```

# Create a custom Id

```js
// Custom _id:
db.students.insertOne(
    {   _id: "student_dev_001",
        name:"user2",
        email:"user2@gamil.com",
        age:25,
        city:"Bangalore",
        Skills:["React","JS"],
        contact:{phone:"5615465165"},
    })
```
# Rules

```js
    db.runCommand({
        collMod:"students",
        validator:{
            $jsonSchema:{
                required:["name","email","age"],
                properties:{
                    name:{bsonType:"string",minLength:1},
                    email:{bsonType:"string",pattern:"^\S+@\S+\.\S+$"}, //regEx + multile chars
                    age:{bsonType:"int",minmum:0},
                    city:{bsonType:["string","null"]},
                    skills:{bsonType:"array"},
                    contact:{bsonType:"Object"}
                    }
                }
            }
        }
    )

// Regx:^S+@\S+\.\S+$ check with `https://regex101.com/`
"^" -> start of the string
"$" -> start of the string

"\S+"
    - \S -> matches any non-whitespace Charater(letter,digits,symbols,etc)
    - + -> means one or more characters

```
