Partie 1 : Préparation
testDB> use schoolDB
switched to db schoolDB
schoolDB> db.createCollection("classes")
{ ok: 1 }
schoolDB>

Partie 2 : Insertion de Données
schoolDB> db.classes.insertOne({
...   className: "Mathematics 101",
...   professor: "John Doe",
...   students: [
...     {
...       name: "Charlie",
...       age: 21,
...       grades: { midterm: 79, final: 92 }
...     },
...     {
...       name: "Dylan",
...       age: 23,
...       grades: { midterm: 79, final: 87 }
...     }
...   ]
... })
...
{
  acknowledged: true,
  insertedId: ObjectId('686a662b0862480cc1baa8ba')
}
schoolDB>

Partie 3 : Requêtes sur Documents Imbriqués
schoolDB> db.classes.find({
...   "students.grades.final": { $gt: 85 }
... })
...
[
  {
    _id: ObjectId('686a662b0862480cc1baa8ba'),
    className: 'Mathematics 101',
    professor: 'John Doe',
    students: [
      { name: 'Charlie', age: 21, grades: { midterm: 79, final: 92 } },
      { name: 'Dylan', age: 23, grades: { midterm: 79, final: 87 } }
    ]
  }
]
schoolDB> db.classes.updateOne(
...   { className: "Mathematics 101" },
...   {
...     $push: {
...       students: {
...         name: "Bob",
...         age: 22,
...         grades: { midterm: 75, final: 85 }
...       }
...     }
...   }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
schoolDB> db.classes.updateOne(
...   {
...     className: "Mathematics 101",
...     "students.name": "Bob"
...   },
...   {
...     $inc: {
...       "students.$.grades.final": 5
...     }
...   }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
schoolDB>

Partie 4 : Ajout et Suppression d'Éléments Imbriqués
schoolDB> db.classes.updateOne(
...   { className: "Mathematics 101" },
...   {
...     $push: {
...       students: {
...         name: "Charlie",
...         age: 23,
...         grades: { midterm: 82, final: 88 }
...       }
...     }
...   }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
schoolDB> db.classes.updateOne(
...   { className: "Mathematics 101" },
...   {
...     $push: {
...       students: {
...         name: "Alice",
...         age: 20,
...         grades: { midterm: 80, final: 90 }
...       }
...     }
...   }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
schoolDB> db.classes.updateOne(
...   { className: "Mathematics 101" },
...   {
...     $pull: {
...       students: { name: "Alice" }
...     }
...   }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
schoolDB>

 Partie 5 : Agrégations (Analyse des Notes)
 schoolDB> db.classes.updateOne(
...   { className: "Mathematics 101" },
...   {
...     $push: {
...       students: {
...         name: "Charlie",
...         age: 23,
...         grades: { midterm: 82, final: 88 }
...       }
...     }
...   }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
schoolDB> db.classes.updateOne(
...   { className: "Mathematics 101" },
...   {
...     $push: {
...       students: {
...         name: "Alice",
...         age: 20,
...         grades: { midterm: 80, final: 90 }
...       }
...     }
...   }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
schoolDB> db.classes.updateOne(
...   { className: "Mathematics 101" },
...   {
...     $pull: {
...       students: { name: "Alice" }
...     }
...   }
... )
...
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
schoolDB> db.classes.aggregate([
...   { $match: { className: "Mathematics 101" } },
...   { $unwind: "$students" },
...   {
...     $group: {
...       _id: "$className",
...       averageFinal: { $avg: "$students.grades.final" }
...     }
...   }
... ])
...
[ { _id: 'Mathematics 101', averageFinal: 89.25 } ]
schoolDB> db.classes.aggregate([
...   { $match: { className: "Mathematics 101" } },
...   { $unwind: "$students" },
...   {
...     $group: {
...       _id: "$className",
...       maxFinal: { $max: "$students.grades.final" }
...     }
...   }
... ])
...
[ { _id: 'Mathematics 101', maxFinal: 92 } ]
schoolDB>

Vérification
schoolDB> db.classes.find().pretty()
[
  {
    _id: ObjectId('686a662b0862480cc1baa8ba'),
    className: 'Mathematics 101',
    professor: 'John Doe',
    students: [
      { name: 'Charlie', age: 21, grades: { midterm: 79, final: 92 } },
      { name: 'Dylan', age: 23, grades: { midterm: 79, final: 87 } },
      { name: 'Bob', age: 22, grades: { midterm: 75, final: 90 } },
      { name: 'Charlie', age: 23, grades: { midterm: 82, final: 88 } }
    ]
  }
]
schoolDB>
