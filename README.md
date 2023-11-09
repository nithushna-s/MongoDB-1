
1. Create a Database called customers.
moviesDB> use customers
switched to db customers

2. Create a collection called customerdetails.
  customers> db.createCollection("customerdetails")
{ ok: 1 }

3. Insert all documents into the collection named  customerdetails.
customers> db.customerdetails.insertMany([{"name":"John","age":"25","gender":"male","city":"new york"},{"name":"Emaily","age":"22","gender":"female","city":"london"},{"name":"deniel","age":"28","gender":"male","city":"syndey"},{"name":"sophia","age":"24","gender":"female","city":"paris"},{"name":"william","age":"26","gender":"male","city":"chicago"},{"name":"olivia","age":"23","gender":"female","city":"los angeles"},{"name":"benjamin","age":"27","gender":"male","city":"toronto"},{"name":"maila","age":"29","gender":"female","city":"berlin"},{"name":"james","age":"30","gender":"male","age":"30","gender":"male","city":"tokyo"}])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("654cb1051046f5637d01e43f"),
    '1': ObjectId("654cb1051046f5637d01e440"),
    '2': ObjectId("654cb1051046f5637d01e441"),
    '3': ObjectId("654cb1051046f5637d01e442"),
    '4': ObjectId("654cb1051046f5637d01e443"),
    '5': ObjectId("654cb1051046f5637d01e444"),
    '6': ObjectId("654cb1051046f5637d01e445"),
    '7': ObjectId("654cb1051046f5637d01e446"),
    '8': ObjectId("654cb1051046f5637d01e447")
  }
}


4. Retrieve all documents from the collection and sort the results by the “age” field    in ascending order.
customers> db.customerdetails.find().sort({ age: 1 }).pretty()
[
  {
    _id: ObjectId("654cb1051046f5637d01e440"),
    name: 'Emaily',
    age: '22',
    gender: 'female',
    city: 'london'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e444"),
    name: 'olivia',
    age: '23',
    gender: 'female',
    city: 'los angeles'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e442"),
    name: 'sophia',
    age: '24',
    gender: 'female',
    city: 'paris'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e43f"),
    name: 'John',
    age: '25',
    gender: 'male',
    city: 'new york'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e443"),
    name: 'william',
    age: '26',
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e445"),
    name: 'benjamin',
    age: '27',
    gender: 'male',
    city: 'toronto'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e441"),
    name: 'deniel',
    age: '28',
    gender: 'male',
    city: 'syndey'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e446"),
    name: 'maila',
    age: '29',
    gender: 'female',
    city: 'berlin'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e447"),
    name: 'james',
    age: '30',
    gender: 'male',
    city: 'tokyo'
  }
]

  
5. Count the number of females.
 customers> db.customerdetails.countDocuments({"gender":"female"})
4

6. Insert one document into the customerdetails collection.
customers> db.customerdetails.insertOne({ "name": "nithu","age":"22","gender":"female","city":"srilanka" }) 
{
  acknowledged: true,
  insertedId: ObjectId("654cb6051046f5637d01e449")
}
customers> db.customerdetails.find().sort({ age: 1 }).pretty()
[
  {
    _id: ObjectId("654cb1051046f5637d01e440"),
    name: 'Emaily',
    age: '22',
    gender: 'female',
    city: 'london'
  },
  {
    _id: ObjectId("654cb6051046f5637d01e449"),
    name: 'nithu',
    age: '22',
    gender: 'female',
    city: 'srilanka'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e444"),
    name: 'olivia',
    age: '23',
    gender: 'female',
    city: 'los angeles'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e442"),
    name: 'sophia',
    age: '24',
    gender: 'female',
    city: 'paris'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e43f"),
    name: 'John',
    age: '25',
    gender: 'male',
    city: 'new york'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e443"),
    name: 'william',
    age: '26',
    gender: 'male',
    city: 'chicago'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e445"),
    name: 'benjamin',
    age: '27',
    gender: 'male',
    city: 'toronto'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e441"),
    name: 'deniel',
    age: '28',
    gender: 'male',
    city: 'syndey'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e446"),
    name: 'maila',
    age: '29',
    gender: 'female',
    city: 'berlin'
  },
  {
    _id: ObjectId("654cb1051046f5637d01e447"),
    name: 'james',
    age: '30',
    gender: 'male',
    city: 'tokyo'
  }
]


7. Update city=SriLanka to John.
customers> db.customerdetails.update({"name":"John"},{$set:{"city":"srilanka"}})
DeprecationWarning: Collection.update() is deprecated. Use updateOne, updateMany, or bulkWrite.
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}

   
8. Remove the customer from Tokyo.
9.  Find customers not from Los Angeles.
10. Find the customers who are older than age 25.
11. Retrieve the males who are less than 25.
12. Update Francis age to 35, if Francis is not available upsert.
13. Retrieve males who are younger than 30 and older than25.
14. Find a customer who is lesser than or equal to 23.
15. Remove the customer from Tokyo.
