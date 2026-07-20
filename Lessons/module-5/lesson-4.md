# Connecting a Flask Server to MongoDB Cluster

## ACS 1710 - Module 5: Lesson 4

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Conceptually create a data query
- Identify relationships in data
- Explain the trade-offs between a SQL and NoSQL database
- Connect a Flask server to a MongoDB cluster

# Video Companions 🎥

<!-- [Setting Up MongoDB Atlas Video](https://youtu.be/0ENeevQ_1e) (recommended before you watch the rest of this lesson) -->

<!-- [Video Lesson](https://file.notion.so/f/f/6004cc36-d69e-461f-a1c5-8e5078ac8f6b/176ba85b-3222-4a08-98f8-2d78692ee243/17_Connecting_to_MongoDB.mov?table=block&id=8d1fb9d4-8241-454d-8ac7-7cffe6e9b1db&spaceId=6004cc36-d69e-461f-a1c5-8e5078ac8f6b&expirationTimestamp=1728064800000&signature=8utux3BOvV_GAYMtio2ljnQc2Mc4Q68wmLqbnIsE3Wk&downloadName=17_Connecting_to_MongoDB.mov) -->

[Video Lesson: MongoDB](https://youtu.be/05_dDRR9TyA)

To create a mongodb "cluster" (this is a database hosted on the mongodb site) follow the guide here: https://www.mongodb.com/docs/guides/atlas/cluster/

# Exercises 💪

Test your understanding of connecting Flask to MongoDB with the questions below. Try to answer each one yourself before checking the answer key.

1. What Flask object property is used to set configuration variables, like the MongoDB connection URI?
2. What line of code creates a `mongo` object capable of interacting with the connected MongoDB database?
3. Once your Flask server is connected to MongoDB, what object must all database operations go through?

<details>
<summary>Answer Key</summary>

1. `app.config`, e.g. `app.config["MONGO_URI"] = "mongodb://localhost:27017/myDatabase"`.
2. `mongo = PyMongo(app)`
3. The `mongo` object (e.g. `mongo.db.collection_name...`).

</details>

# Written Companion 🗒

<aside>
🤔 How do we connect a Flask server with API routes to a MongoDB database cluster?
</aside>

---

The `Flask` object has a built-in property called `config` which allows developers to easily create **configuration variables** (see the **environment variables** lesson for relevant information) with the Python dictionary syntax: `app.config['URL_ROUTE'] = 'URLdestination'`

Using this `config` property, developers can create globally accessible URL connection points to help the Flask server find the MongoDB cluster destination.

<aside>
💡 Once a Flask server gets connected to a MongoDB cluster—we must use the PyMongo library to create a `mongo` object capable of interfacing between the server and database!
</aside>

```python
# create a Flask server, connect it to a MongoDB cluster, then make a mongo object
from flask import Flask
from flask_pymongo import PyMongo

app = Flask(__name__)

# create a configuration variable called MONGO_URI,
# this connects the Flask server to the MongoDB cluster location
app.config["MONGO_URI"] = "mongodb://localhost:27017/myDatabase"

# create a Mongo object using the PyMongo library that can interact with MongoDB
mongo = PyMongo(app)
```

*Fig 1 - importing the Flask and PyMongo Python libraries, creating a Flask server, and connecting the server to the MongoDB database via a `config` variable*

- *Note: all operations between the server and the MongoDB database must be performed through the `mongo` object!*
