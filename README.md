# MongoDB

### Setup

* [MongoDb Download](https://www.mongodb.com/download-center)

MongoDB requires a data folder to store its files. The default location for the MongoDB data directory is c:\data\db.

So create this folder.

To start mondodb -- > goto installed location, ex: C:\Program Files\MongoDB\Server\3.4\bin and execute the command
```
mongod
```
MongoDB started, can execute commands like create DB, Collections, insert, delete, find...

### Commands

Open another command prompt and go to installed location, ex: C:\Program Files\MongoDB\Server\3.4\bin

##### Database
Print a list of all databases on the server.

```
show dbs	
```
Switch current database to <db>. The mongo shell variable db is set to the current database. ex: use mydb
```
use <db>
```
To Drop the database
```
db.dropDatabase()
```

##### Collections

Print a list of all collections in the databse on the server.
```
show collections
```
Create collections .name - Name of the collection to be created, options - document. ex: db.createCollection("mycollection")
```
db.createCollection(name, options)	
```
To Drop Collection
```
db.mycollection.dopr()
```
###### Insert
```
db.mycollection.insert({"name": "Akilan", "age": 27})
or
db.getCollection('mycollection').insert({"name": "Akilan", "age": 27})
```
For Multiple Insert
Must pass objects in array
```
db.mycollection.insert([{"name": "Akilan", "age": 27}, {"name": "Mohan", "age": 28}])
```
###### Find
To Find all docs:
```
db.mycollection.find({})
or
db.getCollection('mycollection').find({})
```
To Find One:
```
db.getCollection('mycollection').findOne({})
```
Find with where clause:
```
db.getCollection('mycollection').find({"name": "Akilan"})
```
Find with AND. by default ',' is considered as AND.:
```
db.getCollection('mycollection').find({"name":"Akilan","age":24})
```
Basic AND Command:
```
db.getCollection('mycollection').find({$and: [{"name": "Akilan"}, {"age":25}]})
```
OR Command:
```
db.getCollection('mycollection').find({$or: [{"name": "Akilan"}, {"age":25}]})
```
###### Update
db.COLLECTION_NAME.update(SELECTION_CRITERIA, UPDATED_DATA)
```
db.getCollection('mycollection').update({"_id":ObjectId("58c61d132dfa01d1eb119ea7")},{$set:{"name":"AKilan Mohan"}})
```

###### Save
The save() method replaces the existing document with the new document passed in the save() method
```
db.COLLECTION_NAME.save({id,NEW_DATA})
```
