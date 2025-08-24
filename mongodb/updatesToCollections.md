# Updates to the Collection
# link
https://www.mongodb.com/docs/manual/reference/method/db.collection.updateMany/

## Updates : updateOne,updateMany,replaceOne
### updateOne
```js

db.students.updateOne(
    {email:"m@gmail.com"},
    {$set:{city:"Chennai","contact.phone":"2151516544"}}
);
db.students.updateOne({name:/saravanan/i},
                      {$set:{email:"saravanan.yahoo.com",Skills:["Node","JS"]}}
                       );
```

### updateMany

```js

db.students.updateMany(
{},
{$set:{createAt:new Date()}}
);
```

### Replace

```js

db.students.replaceOne(
{email:"s@gmail.com"},
{name:"saravanan",email:"sdkfjhds@gmail.com",age:21,city:"chennai",createAt:new Date(),skills:["JS","Node"]}
);
```

### in UpdateOne how to push,pull inside the array and objects
<!-- Objects -->
```js
db.students.updateOne(
    {email:"m@gmail.com"},
    {$set:{city:"Chennai","contact.phone":"2151516544"}}
);
```
<!-- Array -->
```js
// it willl create duplicates
db.students.updateOne(
{email:"s@gmail.com"},
{$push:{skills:"React"}}
);
// avoid the Duplicates
db.studends.updateOne(
{email:"s@gmail.com"},
{$addToSet:{skills:"React"}}
)
// How to remove

db.studends.updateOne(
{email:"s@gmail.com"},
{$pull:{skills:"React"}}
)
```
# delete the particular document in specific object or array:
```js

db.studends.updateOne(
{email:"saravanan@gmail.com"},
{$unset:{contact:""}}
)
```
