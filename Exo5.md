
test> db.realEstate.insertMany([
...   { name: "House A", z...   { name: "House A", z1, price: 600000 },
...   { name: "House B"...   { name: "House 3, price: 320000 },
...   { name: "House...   { name: "House8, price: 400000 }
... ])
...
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('686aa56770b671d7aebaa8b9'),
    '1': ObjectId('686aa56770b671d7aebaa8ba'),
    '2': ObjectId('686aa56770b671d7aebaa8bb')
  }
}
test> db.realEstate.insertMany([
...   { name: "House A", zipCode: 75001, price: 600000 },
...   { name: "House B", zipCode: 69003, price: 320000 },
...   { name: "House C", zipCode: 13008, price: 400000 }
... ])
...
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('686aa56c70b671d7aebaa8bc'),
    '1': ObjectId('686aa56c70b671d7aebaa8bd'),
    '2': ObjectId('686aa56c70b671d7aebaa8be')
  }
}
test>
