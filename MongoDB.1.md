# MongoDB

- **Document** database.
- Stores data in a type of JSON format called **BSON**.

## Terms
|SQL|MongoDB|
|--|--|
|Tables|Collections|
|Records|Documents|
|Columns|Fields|
|Index|Index|
|Table Joins|`$lookup`|

## SQL vs. Document Databases
- SQL databases are relational databases. They store related data in separate tables. It is quried from multiple tables to join the data back together.
- Document databases, also known as non-relational or non-tabular databases, store related data in flexible documents. They keep all related data together, which makes reading data very fast.

## Commands
|Description|Command|
|--|--|
|Get Available Databases|`show dbs`|
|Create Database|`use xxx`|
|Create Collection|- `db.createCollection('xxx')` - `db.xxx.insertOne(object)`|
|Insert Single Document|`db.xxx.insertOne(object)`|
|Insert Multiple Documents|`db.xxx.insertMany(object[])`|
|Get Single (First) Document|`db.xxx.findOne()`|
|Get Documents|`db.xxx.find()`|
|Update Single (First) Document|`db.xxx.updateOne({filter}, {$set: {updatedObject})`|
|Update Multiple Documents|`db.xxx.updateMany({filter}, {operator})`|
|Delete Single (First Document)|`db.xxx.deleteOne({filter})`|
|Delete Multiple Documents|`db.xxx.deleteMany({filter})`|

## Projection
- `db.xxx.find()` and `db.xxx.findOne()` accept a second parameter called `projection`. 
- It is an object that describes which **fields to include** in the results. 
- It is optional.
- `1` to include a field; `0` to exclude a field.
- Cannot use both `0` and `1` in the same object. Only exception is the `_id` field. For example, `db.xxx.find({}, {title: 1, date: 0})`.

## Update Documents
- `{upsert: true}` to insert the document if it is not found.

## Query Operators
### Comparison
|Description|Operator|
|--|--|
|Equal|`$eq`|
|Not Equal|`$ne`|
|Greater Than|`$gt`|
|Greater Than or Equal|`$gte`|
|Less Than|`$lt`|
|Less Than or Equal|`$lte`|
|Matched within Array|`$in`|

### Logical
|Description|Operator|
|--|--|
|Both Queries Match|`$and`|
|Either Query Matches|`$or`|
|Both Queries Not Match|`$nor`|
|Query Not Match|`$not`|

### Evaluation
|Description|Operator|
|--|--|
|Regrex when Evaluating|`$regrex`|
|Text Search|`$text`|
|JavaScript to Match Documents|`$where`|

## Update Operators

### Fields
|Description|Operator|
|--|--|
|Current Data|`$currentData`|
|Increment|`$inc`|
|Rename|`$rename`|
|Set Value|`$set`|
|Remove Fields|`$unset`|

### Array
|Description|Operator|
|--|--|
|Add Distinct Elements|`$addToSet`|
|Remove First or Last Element|`$pop`|
|Remove All Elements with Matched Query|`$pull`|
|Add An Element`$push`|
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjMwMjQxNjUzXX0=
-->