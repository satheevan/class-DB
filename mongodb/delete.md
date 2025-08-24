# Delete
```js
db.students.updateOne(
    { email: "sa@gmail.com" },
    { $unset: { contact: "" }}
);

db.students.deleteOne({ email: "sa@gmail.com" });

db.students.deleteMany({ city: "Bengaluru" });
```