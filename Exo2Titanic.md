
TestedDB> db.Passengers.updateMany(
...   { $or: [
...       { Embarked: "" },
...       { Embarked: null },
...       { Embarked: { $exists: false } }
...     ]
...   },
...   { $set: { Embarked: "S" } }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 0,
  modifiedCount: 0,
  upsertedCount: 0
}
TestedDB>
(To exit, press Ctrl+C again or Ctrl+D or type .exit)
TestedDB> db.Passengers.updateMany(
...   { Survived: "1" },
...   { $set: { rescued: true } }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 0,
  modifiedCount: 0,
  upsertedCount: 0
}
TestedDB> db.Passengers.find(
...   { Age: { $ne: "" } },
...   { Name: 1, Age: 1 }
... ).sort({ Age: 1 }).limit(10)
... db.Passengers.find(
...   { Age: { $ne: "" } },
...   { Name: 1, Age: 1 }
... ).sort({ Age: 1 }).limit(10)
...

TestedDB> db.Passengers.find(
...   { Survived: "0", Pclass: "2" },
...   { Name: 1, Pclass: 1, Survived: 1 }
... )
...

TestedDB> db.Passengers.deleteMany(
...   { Survived: "0", $or: [ { Age: "" }, { AgeAge: null }, { Age: { $exists: false } } ] }
... )
...
{ acknowledged: true, deletedCount: 0 }
TestedDB> db.Passengers.updateMany(
...   { Age: { $type: "double" } },
...   { $inc: { Age: 1 } }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 0,
  modifiedCount: 0,
  upsertedCount: 0
}
TestedDB> db.Passengers.deleteMany(
...   { $or: [ { Ticket: "" }, { Ticket: { $exis$exists: false } } ] }
... )
...
{ acknowledged: true, deletedCount: 0 }
TestedDB> db.Passengers.find(
...   { Name: /Dr\./i }
... )
...

TestedDB> db.Passengers.find().pretty()

TestedDB> db.Passengers.countDocuments()
0
TestedDB>
