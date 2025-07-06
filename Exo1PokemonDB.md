ls@DESKTOP-EJRP3Q0:~$ head -n 1 /mnt/c/Users/PRETORIUS/Downloads/pokemonGO.csv
"PokemonNo ,Name,Type 1,Type 2,Max CP,Max HP,Image URL"
ls@DESKTOP-EJRP3Q0:~$ mongoimport --type csv -d PokemonDB -c Pokemons --headerline --file /mnt/c/Users/PRETORIUS/Downloads/pokemonGO.csv
2025-07-06T12:43:38.763+0200    connected to: mongodb://localhost/
2025-07-06T12:43:38.778+0200    151 document(s) imported successfully. 0 document(s) failed to import.
ls@DESKTOP-EJRP3Q0:~$ mongosh
use PokemonDB
db.Pokemons.find().pretty()
Current Mongosh Log ID: 686a536e87dd772c91baa8b8
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

test> use PokemonDB
switched to db PokemonDB
PokemonDB> db.Pokemons.find().pretty()
[
  {
    _id: ObjectId('686a527d9bcebf903184f25a'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '004,Charmander,Fire,,962,73,http://cdn.bulbagarden.net/upload/thumb/7/73/004Charmander.png/250px-004Charmander.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f25b'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '002,Ivysaur,Grass,Poison,1643,107,http://cdn.bulbagarden.net/upload/thumb/7/73/002Ivysaur.png/250px-002Ivysaur.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f25c'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '005,Charmeleon,Fire,,1568,103,http://cdn.bulbagarden.net/upload/thumb/4/4a/005Charmeleon.png/250px-005Charmeleon.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f25d'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '006,Charizard,Fire,Flying,2620,135,http://cdn.bulbagarden.net/upload/thumb/7/7e/006Charizard.png/250px-006Charizard.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f25e'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '007,Squirtle,Water,,1015,81,http://cdn.bulbagarden.net/upload/thumb/3/39/007Squirtle.png/250px-007Squirtle.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f25f'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '008,Wartortle,Water,,1594,105,http://cdn.bulbagarden.net/upload/thumb/0/0c/008Wartortle.png/250px-008Wartortle.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f260'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '009,Blastoise,Water,,2560,137,http://cdn.bulbagarden.net/upload/thumb/0/02/009Blastoise.png/250px-009Blastoise.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f261'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '001,Bulbasaur,Grass,Poison,1079,83,http://cdn.bulbagarden.net/upload/thumb/2/21/001Bulbasaur.png/250px-001Bulbasaur.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f262'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '003,Venusaur,Grass,Poison,2598,138,http://cdn.bulbagarden.net/upload/thumb/a/ae/003Venusaur.png/250px-003Venusaur.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f263'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '010,Caterpie,Bug,,446,83,http://cdn.bulbagarden.net/upload/thumb/5/5d/010Caterpie.png/250px-010Caterpie.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f264'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '012,Butterfree,Bug,Flying,1465,107,http://cdn.bulbagarden.net/upload/thumb/d/d1/012Butterfree.png/250px-012Butterfree.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f265'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '013,Weedle,Bug,Poison,452,75,http://cdn.bulbagarden.net/upload/thumb/d/df/013Weedle.png/250px-013Weedle.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f266'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '011,Metapod,Bug,,481,91,http://cdn.bulbagarden.net/upload/thumb/c/cd/011Metapod.png/250px-011Metapod.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f267'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '014,Kakuna,Bug,Poison,488,83,http://cdn.bulbagarden.net/upload/thumb/f/f0/014Kakuna.png/250px-014Kakuna.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f268'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '015,Beedrill,Bug,Poison,1450,115,http://cdn.bulbagarden.net/upload/thumb/6/61/015Beedrill.png/250px-015Beedrill.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f269'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '018,Pidgeot,Normal,Flying,2106,143,http://cdn.bulbagarden.net/upload/thumb/5/57/018Pidgeot.png/250px-018Pidgeot.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f26a'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '016,Pidgey,Normal,Flying,684,75,http://cdn.bulbagarden.net/upload/thumb/5/55/016Pidgey.png/250px-016Pidgey.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f26b'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '017,Pidgeotto,Normal,Flying,1232,111,http://cdn.bulbagarden.net/upload/thumb/7/7a/017Pidgeotto.png/250px-017Pidgeotto.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f26c'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '020,Raticate,Normal,,1454,99,http://cdn.bulbagarden.net/upload/thumb/f/f4/020Raticate.png/250px-020Raticate.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f26d'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '019,Rattata,Normal,,585,59,http://cdn.bulbagarden.net/upload/thumb/4/46/019Rattata.png/250px-019Rattata.png'
    }
  }
]
Type "it" for more
PokemonDB> db.Pokemons.find({ "Type 1": "Fire" }).pretty()

PokemonDB> db.Pokemons.countDocuments()
302
PokemonDB> db.Pokemons.find({ "Max CP": { $gt: 3000 } }).pretty()

PokemonDB> db.Pokemons.find().sort({ "Max CP": -1 }).limit(5).pretty()
[
  {
    _id: ObjectId('686a527d9bcebf903184f25d'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '006,Charizard,Fire,Flying,2620,135,http://cdn.bulbagarden.net/upload/thumb/7/7e/006Charizard.png/250px-006Charizard.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f25e'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '007,Squirtle,Water,,1015,81,http://cdn.bulbagarden.net/upload/thumb/3/39/007Squirtle.png/250px-007Squirtle.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f25b'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '002,Ivysaur,Grass,Poison,1643,107,http://cdn.bulbagarden.net/upload/thumb/7/73/002Ivysaur.png/250px-002Ivysaur.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f25a'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '004,Charmander,Fire,,962,73,http://cdn.bulbagarden.net/upload/thumb/7/73/004Charmander.png/250px-004Charmander.png'
    }
  },
  {
    _id: ObjectId('686a527d9bcebf903184f25c'),
    PokemonNo: {
      ',Name,Type 1,Type 2,Max CP,Max HP,Image URL': '005,Charmeleon,Fire,,1568,103,http://cdn.bulbagarden.net/upload/thumb/4/4a/005Charmeleon.png/250px-005Charmeleon.png'
    }
  }
]
PokemonDB> db.Pokemons.insertOne({
...   name: "Pikachu",
...   type: "Électrik",
...   CP: 500
... })
...
{
  acknowledged: true,
  insertedId: ObjectId('686a54c587dd772c91baa8b9')
}
PokemonDB> db.Pokemons.insertOne({
...   name: "Pikachu",
...   type: "Électrik",
...   CP: 500
... })
...
{
  acknowledged: true,
  insertedId: ObjectId('686a54de87dd772c91baa8ba')
}
PokemonDB> db.Pokemons.updateOne(
...   { name: "Pikachu" },
...   { $set: { CP: 900 } }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
PokemonDB> db.Pokemons.findOne({ name: "Pikachu" })
{
  _id: ObjectId('686a54c587dd772c91baa8b9'),
  name: 'Pikachu',
  type: 'Électrik',
  CP: 900
}
PokemonDB> db.Pokemons.deleteOne({ name: "Bulbasaure" })
{ acknowledged: true, deletedCount: 0 }
PokemonDB> db.Pokemons.find({ name: "Bulbasaure" })

PokemonDB> show dbs
PokemonDB   88.00 KiB
admin       40.00 KiB
config     108.00 KiB
local       72.00 KiB
PokemonDB> show collections
Pokemons
PokemonDB> db.Pokemons.countDocuments()
304
PokemonDB>
