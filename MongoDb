// Display all databases
show dbs

// Switch to a specific database or create a new one
use myDatabase

// Display all collections in the current database
show collections

// Insert a single document into a collection
db.myCollection.insertOne({ key: "value" })

// Insert multiple documents into a collection
db.myCollection.insertMany([{ key1: "value1" }, { key2: "value2" }])

// Query for documents in a collection
db.myCollection.find()

// Update a document in a collection
db.myCollection.updateOne({ key: "value" }, { $set: { key: "new_value" } })

// Remove a document from a collection
db.myCollection.deleteOne({ key: "value" })

// Create an index on a field
db.myCollection.createIndex({ key: 1 })

// Display existing indexes on a collection
db.myCollection.getIndexes()

// Drop an index from a collection
db.myCollection.dropIndex("index_name")
 

//start mongodb 
mongod --dbpath data

mongoimport --db opendata --collection atlenergy < energy_wb.json

#restore database from mongodump
mongorestore --collection col --db opendata opendata/col.bson




//create new colletion
db.createCollection("log", { capped : true, size : 5242880, max : 5000 } )

db.createCollection("cars", { "_id" : 100, "name" : "GTO", "year" : 1969, "color" : "red" } )


db.products.insert( { item: "card", qty: 15 } )

db.cars.insert( { "_id" : 100, "name" : "GTO", "year" : 1969, "color" : "red" } )


//Which of the following statements would set "available" to 1?


db.cars.update({_id:100},{$set:{available:1}})

db.cars.update({_id:100},{$inc:{available:1}})

db.cars.update({},{$inc:{available:1,year:1970}})

//All work

//remove collections
db.collection.remove( {_id : 100} )
db.users.remove({"addr.city":"Lyon", registered:false})

db.users.update({_id:"Jane"},{$addToSet:{likes:"football"}}, true)


// suggested shell cmd line to run this:
//   map reduce function
//   mongo --shell example2.js
// 
// Note: the { out : … } parameter is for mongodb 1.8+
 
db.things.insert( { _id : 1, tags : ['dog', 'cat'] } );
db.things.insert( { _id : 2, tags : ['cat'] } );
db.things.insert( { _id : 3, tags : ['mouse', 'cat', 'dog'] } );
db.things.insert( { _id : 4, tags : []  } );
 
// map function
m = function(){
    this.tags.forEach(
        function(z){
            emit( z , { count : 1 } );
        }
    );
};
 
// reduce function
r = function( key , values ){
    var total = 0;
    for ( var i=0; i<values.length; i++ )
        total += values[i].count;
    return { count : total };
};
 
res = db.things.mapReduce(m, r, { out : "myoutput" } );
 
printjson(res);
 
print("try db.myoutput.find()");

//geospatial index 

loc : { lng : <longitude> , lat : <latitude> }

//geo ref
http://docs.mongodb.org/manual/core/2d/

db.combo.find({$or:[{state: "VA"}, {commercial: {$lt: 30.0} }]} ).sort({commercial: 1})

db.combo.find({commercial: {$lt: 9.0}}, {State: 1,commercial:1, _id:0}).sort({commercial:1})
 db.combos.find({industrial:{$lte:5.0}} )

