# Queries Basics
<!-- https://www.w3schools.com/mongodb/mongodb_query_operators.php -->
# find All

```js
db.students.find();

// value is there
db.students.find({updatedAt:{$exists:true}});
```

# greater than  and less that
```js
db.students.find({age : {$gte:21}});

db.students.find({age : {$gte:20,$lt:25}});

```

# Projection:

# print only few feilds
```js
db.students.find(
    {age:{$gte:21}},
    {name:1,city:1,_id:0} //1 is used to visible and disable the _id
    );
```
# print All the feilds, some feilds will eliminate
```js
db.students.find(
    {}, // it will list all the element
    {contact:0} // only contact will not show
    );
```
# sorting and pagination

```js
db.students.find().sort({
    age:-1 //-1 decending and 1 ascending order
}).limit(3)
// page :2, 3-per-page(skip the first 3, then true) offset
db.students.find().sort({age:-1}).skip(3).limit(3) //-1 is for ascending order

```
# Case insensitive Search

```js
// one of the way RegEX
// eg: Email ending with @example.com
db.students.find({email: /@example\.com$/i})
```
## localization - TODO 

## Dates

### Create date
```js
    // its object like bson
    db.students.insertOne({
        name:"saravanan",
        email:"saravanan@gamil.com",
        age:25,
        city:"Bangalore",
        Skills:["React","JS"]
        contact:{phone:"5615465165"}
        createdAt : new Date() //utc time zone
    });
```
### sorting date 

```js
db.students.find().sort({
    createAt:-1 //-1 is for ascending order
}).limit(5)

```
### student created at last 7 days

```js

// new Date() -> it current date
// new Date(Date.now() - 7*24*60*60*1000)-> Date.now is create instance and subract the given value

db.students.find({
    createAt:{$gte:new Date(Date.now()-7*24*60*60*1000)}})

```
# Filter

```javascript
// searching for key and value in object
db.students.find({"constact.phone":"5615465165"});

// searching for single element in array
db.students.find({skills:"React"});
// Require multiple element in array
db.students.find({skills:{$all:["React","JS"]}});

```