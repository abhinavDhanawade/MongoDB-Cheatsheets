# **MongoDB Cheat Sheet**
#### **Database Management**:
1. Switch to a specific database.
    ```
    use <database>
    ```
2. List all available databases.
    ```
    show dbs
    ```
3. Display the current database.
    ```
    db
    ```
4. Delete the current database.
    ```
    db.dropDatabase(): 
    ```
5. Display statistics about the current database.
    ```
    db.stats()
    ```
6. Show the MongoDB server version.
    ```
    db.version() 
    ```
7. Display the current MongoDB connection string.
    ```
    db.getMongo()
    ```

#### **Collection Operations**:

1. Create a new collection in the current database. 
    ```
    db.createCollection("<collection>")
    ```
2. Get a reference to a specific collection.
    ```
    db.getCollection("<collection>")
    ```
3. List all collections in the current database.
    ```
    db.getCollectionNames()
    ```
4. Drop/delete a collection.
    ```
    db.collection.drop()
    ```
5. Show collections.
    ```
    show collections
    ```

#### **Document Operations**:

1. Retrieve all documents in a collection.
    ```
    db.<collection>.find()
    ```
    ```
    db.<collection>.find().pretty()
    ```
2. Retrieve a single document from a collection.
    ```
    db.<collection>.findOne()
    ```
3. Insert a new document into a collection.
    ```
    db.<collection>.insertOne(<document>)
    ```
4. Insert multiple documents into a collection.
    ```
    db.<collection>.insertMany([<document1>, <document2>, ...])
    ```
5. Update a single document that matches the filter.
    ```
    db.<collection>.updateOne(<filter>, <update>)
    ```
6. Update multiple documents that match the filter.
    ```
    db.<collection>.updateMany(<filter>, <update>)
    ```
7. Delete a single document that matches the filter.
    ```
    db.<collection>.deleteOne(<filter>)
    ```
8. Delete multiple documents that match the filter.
    ```
    db.<collection>.deleteMany(<filter>)
    ```
9. Retrieve sorted documents from a collection.
    ```
    # asc
    db.<collection>.find().sort({ title: 1 }).pretty()
    ```
    ```
    # desc
    db.<collection>.find().sort({ title: -1 }).pretty()
    ```
10. Retrieve documents count from a collection.
    ```
    db.<collection>.find().count()
    ```
11. Retrieve limited documents from a collection.
    ```
    db.<collection>.find().limit(2).pretty()
    ```
12. Retrieve documents from a collection using chaining of methods.
    ```
    db.<collection>.find().limit(2).sort({ title: 1 }).pretty()
    ```

#### **User Management**:
1. Create a new user for the current database.
    ```
    db.createUser({<user document>})
    ```
2. Update an existing user.
    ```
    db.updateUser("<username>", {<user document>})
    ```
3. Delete a user from the current database.
    ```
    db.dropUser("<username>")
    ```
4. Change the password for a user.
    ```
    db.changeUserPassword("<username>", "<newPassword>")
    ```

#### **Indexing**:
1. Create an index on specified keys of a collection.
    ```
    db.collection.createIndex(<keys>)
    ```
2. List all indexes in a collection.
    ```
    db.collection.getIndexes()
    ```
3. Drop/delete an index from a collection.
    ```
    db.collection.dropIndex("<indexName>")
    ```

#### **Backup and Restore**:
1. Create a binary export of the entire MongoDB instance or a specific database.
    ```
    mongodump
    ```
2. Restore data from a binary export created by mongodump.
    ```
    mongorestore
    ```


#### **Comparison Operators**:

- $eq : Matches values that are equal to a specified value.

- $ne: Matches values that are not equal to a specified value.

- $gt: Matches values that are greater than a specified value.

- $gte: Matches values that are greater than or equal to a specified value.

- $lt: Matches values that are less than a specified value.

- $lte: Matches values that are less than or equal to a specified value.

- $in: Matches any of the values specified in an array.

- $nin: Matches none of the values specified in an array.
#### **Logical Operators**:

- $and: Joins query clauses with a logical AND.

- $or: Joins query clauses with a logical OR.

- $not: Inverts the effect of a query expression.

- $nor: Joins query clauses with a logical NOR (none of the conditions match).

#### **Element Operators**:

- $exists: Matches documents that have the specified field.

- $type: Matches documents that have a field of the specified type.

#### **Array Operators**:

- $all: Matches arrays that contain all the specified elements.

- $elemMatch: Matches arrays that contain at least one element matching all the specified criteria.

- $size: Matches arrays with a specific number of elements.

#### **Text Search Operators**:

- $text: Performs a text search on a field.

- $search: Performs a text search using a specified search string.

#### **Regular Expression Operators**:

- $regex: Matches documents based on a specified regular expression pattern.

- $options: Specifies options for the regular expression pattern.

#### **Geospatial Operators**:

- $geoWithin: Selects geometries within a bounding GeoJSON geometry.

- $geoIntersects: Selects geometries that intersect with a GeoJSON geometry.

- $near: Returns documents near a specific location.

#### **Projection Operators**:

- $project: Specifies which fields to include or exclude in the query result.
