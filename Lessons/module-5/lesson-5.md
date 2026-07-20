# Performing C.R.U.D Operations with PyMongo

## ACS 1710 - Module 5: Lesson 5

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Use `insert_one()` to create a new document in a MongoDB collection.
- Use `find()` and `find_one()` to read documents from a MongoDB collection.
- Use `update_one()` to modify an existing document in a MongoDB collection.
- Use `delete_one()` to remove a document from a MongoDB collection.

# Video Companions 🎥

<!-- [Video 1 - Performing C.R.U.D. operations to a MongoDB cluster via Flask and PyMongo](https://file.notion.so/f/f/6004cc36-d69e-461f-a1c5-8e5078ac8f6b/c6b33d5f-0398-4a3a-85c9-d3ae0c7078db/18_PyMongo_and_CRUD.mov?table=block&id=51a4c123-a8ca-4d6e-87a3-4301159f6383&spaceId=6004cc36-d69e-461f-a1c5-8e5078ac8f6b&expirationTimestamp=1728064800000&signature=zKM9E-X3IoiozPCnahLLGKpRS_pyHKWJYM_yyd7h0KM&downloadName=18_PyMongo_and_CRUD.mov) -->

[Video 1 - Performing C.R.U.D. operations to a MongoDB cluster via Flask and PyMongo](https://youtu.be/eiJJq86zmmI)

# Exercises 💪

Test your understanding of C.R.U.D operations in PyMongo with the questions below. Try to answer each one yourself before checking the answer key.

1. Which PyMongo method inserts a single new document into a collection? Which one inserts several documents at once?
2. What does `mongo.db.users.find()` return when called with no arguments?
3. What's the difference between `find()` and `find_one()`?
4. What two arguments does `update_one()` take, and what does each one do?
5. What does the `$set` operator do inside an `update_one()` call?

<details>
<summary>Answer Key</summary>

1. `insert_one(data)` inserts a single document; `insert_many(data)` inserts several documents at once.
2. All documents in the `users` collection.
3. `find()` returns all matching documents; `find_one()` returns only the first matching document.
4. A `searchParam` (which document(s) to find) and a `changes` object (what to update them to) — e.g. `update_one(searchParam, changes)`.
5. It sets an existing field to a new given value.

</details>

# Written Companion 🗒

<aside>
🤔 How do we use MongoDB in Python, and how can we connect a Flask server to a MongoDB database?
</aside>

---

The four primary operations that can be performed in a database can be described using the acronym **C.R.U.D:**

- create - the act of creating new collections or inserting new documents into a collection
- read - finding and retrieving documents/collections from the database for processing
- update - modifying a currently existing document or collection
- delete - removing a document or collection from the database

### Create = `insert_one()` and `insert_many()` in PyMongo

To **create** a new document within a MongoDB collection, the `insert_one(data)` or `insert_many(data)` methods must be used.

```python
# creating a new Python dictionary called `new_user`
new_user = {
   'first_name': 'Jay',
   'role': 'instructor',
   'teaches': 'WEB 1.1'
}

# insert this document into the mongo database collection called `users`
result = mongo.db.users.insert_one(new_user)
```

*Fig 1 - using the `insert_one` method to insert a Python dictionary object as a MongoDB document into the `users` collection.*

- *Note: since an `_id`* property did not get assigned an `ObjectId` value, MongoDB will create a default `_id`

### Read = `find()` in PyMongo

To **read** an existing document within a MongoDB collection, the `find(searchParam)` method must be used.

Using the `find()` method without any parameters will default to reading **all documents** in the collection.

Passing a specific **key-value** pair as a parameter to `find(searchParam)` will only return documents that contain a matching property.

```python
# reading all documents in a collection and printing the results
all_users = mongo.db.users.find()
for user in all_users:
   print(user['name'])

# reading documents that have a `role` of `instructor
all_instructors = mongo.db.users.find({'role': 'instructor'})
for user in all_instructors:
   print(user['name'])
```

*Fig 2 - using `find()` with and without a `searchParam`*

<aside>
🚨 If you only want the first matching document of your `find()` parameter to be returned (instead of all matching documents)—use `find_one(searchParam)` instead of `find(searchParam)`.
</aside>

### Update = `update_one()` in PyMongo

To **update** an existing document within a MongoDB collection, the `update_one(searchParam, changes)` method must be used.

<aside>
💡 In many ways, **updating** combines **reading** and **creating**. We must first pass the `update_one()` a `searchParam` to find the data to update—then modify the found data with the `changes` object.
</aside>

The `changes` update can perform many operations. Some of the most common include:

- `$set` = set old value to the new given value
- `$inc` = increment the found value by one
- `$regex` = utilize a regular expression

```python

# finding a document and updating it with changes
searchParam = { 'first_name': 'Jay' }
changes = {'$set': { 'role': 'CEO' }}
user1 = mongo.db.users.update_one(searchParam, changes)
```

*Fig 3 - using `update_one()` to perform a **change** in MongoDB*

- Note: *searchParam and changes get defined separate from `update_one()` in this example to make seeing the data easier. These can be written write into the `update_one()` function as well.*

### Delete = `delete_one()` in PyMongo

To **delete** an existing document within a MongoDB collection, the `delete_one(searchParam)` method must be used.

```python
# removing the document with a `first_name` of `Jay` from the users collection
result = mongo.db.users.delete_one({
   'first_name': 'Jay'
})
print(result.deleted_count)

>>> 1
```

*Fig 4 - deleting a document using `delete_one()`*

- *Note: the result returned after most operations will either be a 1 (for success) or an error number (for failure)*
