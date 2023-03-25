## 1.Introduction to MongoDB
>This course is broken down into the following units:

 1. Unit 01: Getting Started with    MongoDB Atlas, the Developer Data  Platform
 2. Unit 02: Overview of MongoDB and the Document Model
 3. Unit 03: Connecting to a MongoDB Database
 4. Unit 04: MongoDB CRUD Operations: Insert and Find Documents
 5. Unit 05: MongoDB MongoDB CRUD: Replace and Delete
 6. Unit 06: MongoDB CRUD Operations:  Modifying Query Results
 7. Unit 07: MongoDB Aggregation
 8. Unit 08: MongoDB Indexing
 9. Unit 09: MongoDB Atlas Search
 10. Unit 10: Introduction to MongoDB Data Modeling
11. Unit 11: MongoDB Transactions

## 2.Mongodb and the Document Model
1. MongoDB is a general purpose document database
3. Documents offer a flexable and    developer-friendly way to Work with data
4. document is a basic unit of data in mongodb
5. collection is a group of this document
6. Database container for collection
7. The MongoDB database is at the core of MongoDB Atlas
>Usecase example
1. E-commerce
2. Content Mangement
3. IOT and time-series data
4. Trading and Payments
5. Gaming
6. Mobile Apps
7. Real-time analytics and AI

>key points
1. Display documents in JSON in mongodb
2. Stored documents in BSON in mongodb:Adds supports data types unavailable in JSON like types,dates,numbers and ObjectIds.
3. The values in a document can be any data type, including strings, objects, arrays, booleans, nulls, dates, ObjectIds, and more.

>Basic commands
``` javascript
// create database
use ecom

// create collection
db.createCollection('products');

//show collections
show collections

// delate collection
db.products.drop()

//delete database
db.dropDatabase()

```
## 3.CRUD Operation
1. insertOne and insertMany
``` javascript
// insert one
db.products.insertOne({name:'keyboard',price:250})

//insertMany: Array of object
db.products.insertMany([
 {name:'keyboard',price:250,rate:54},
 {name:'keyboard',price:250,rate:54}])
```
2. Read data 
```javascript
// Return all documents
   db.products.find() 
// return first match document
db.products.find({name:"keyboard"})

```
>Use the $in operator to select documents where the value of a field equals any value in the specified array. Here's an example:
``` javascript
db.zips.find({ city: { $in: ["PHOENIX", "CHICAGO"] } })
```
>Finding Documents by Using Comparison Operators
1. $gt
```javascript
//Use the $gt operator to match documents with a field greater than the given value
db.sales.find({ "items.price": { $gt: 50}})
```
2. $lt
``` javascript
//Use the $lt operator to match documents with a field less than the given value. 
db.sales.find({ "items.price": { $lt: 50}})
```
3. $lte
``` javascript
//Use the $lte operator to match documents with a field less than or equal to the given value
db.sales.find({ "customer.age": { $lte: 65}})
```
4.$gte
```javascript
//Use the $gte operator to match documents with a field greater than or equal to the given value.
db.sales.find({ "customer.age": { $gte: 65}})
```
