Partie 1 : Exploration des Bases de Données et Collections
ls@DESKTOP-EJRP3Q0:~$ mongosh
Current Mongosh Log ID: 686a61170862480cc1baa8b8
Connecting to:          mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+2.5.3
Using MongoDB:          8.0.10
Using Mongosh:          2.5.3
mongosh 2.5.5 is available for download: https://www.mongodb.com/try/download/shell

For mongosh info see: https://www.mongodb.com/docs/mongodb-shell/

------
   The server generated these startup warnings when booting
   2025-07-06T03:13:29.426+02:00: Using the XFS filesystem is strongly recommended with the WiredTiger storage engine. See http://dochub.mongodb.org/core/prodnotes-filesystem
   2025-07-06T03:13:33.658+02:00: Access control is not enabled for the database. Read and write access to data and configuration is unrestricted
   2025-07-06T03:13:33.664+02:00: For customers running the current memory allocator, we suggest changing the contents of the following sysfsFile
   2025-07-06T03:13:33.664+02:00: We suggest setting the contents of sysfsFile to 0.
   2025-07-06T03:13:33.666+02:00: We suggest setting swappiness to 0 or 1, as swapping can cause performance problems.
------

test> show dbs
PokemonDB   88.00 KiB
TitanicDB   68.00 KiB
admin       40.00 KiB
config     108.00 KiB
local       72.00 KiB
test> use testDB
switched to db testDB
testDB> db.createCollection("testCollection")
{ ok: 1 }
testDB> show collections
testCollection
testDB>

 Partie 2 : Manipulation des Données
 testDB> db.testCollection.insertOne({ name: "test", value: 1 })
{
  acknowledged: true,
  insertedId: ObjectId('686a62220862480cc1baa8b9')
}
testDB> db.testCollection.find()
[
  { _id: ObjectId('686a62220862480cc1baa8b9'), name: 'test', value: 1 }
]
testDB> db.testCollection.updateOne({ name: "test" }, { $inc: { value: 1 } })
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
testDB> db.testCollection.find()
[
  { _id: ObjectId('686a62220862480cc1baa8b9'), name: 'test', value: 2 }
]
testDB> db.testCollection.deleteOne({ name: "test" })
{ acknowledged: true, deletedCount: 1 }
testDB> db.testCollection.find()

testDB>

 Partie 3 : Nettoyage
 
testDB> db.testCollection.drop()
true
testDB> db.dropDatabase()
{ ok: 1, dropped: 'testDB' }
testDB> show dbs
PokemonDB   88.00 KiB
TitanicDB   68.00 KiB
admin       40.00 KiB
config     108.00 KiB
local       72.00 KiB
testDB>

