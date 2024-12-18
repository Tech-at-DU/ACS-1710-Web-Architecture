# Homework 5: Databases

## Purpose (Why should I do this?)

When writing your own web applications, you will nearly always need a database of some sort. This assignment will allow you to practice using the MongoDB database to create, read, update, and delete objects, as well as model one-to-many relationships.

Scoring for this project is as follows:

| Score | Rating | Correctness | Code Quality |
| :---: | :----: | :---------: | :----------: |
| **1** | **Needs Improvement** | Required sections of submission are largely missing or not functional. | Code is messy and hard to follow. Code includes TODOs or does not include docstrings for most routes. |
| **2** | **Basic** | Most routes are functional, but a few may be hard-coded or incorrect. | Some routes have code that is messy and hard to follow. Some routes do not include docstrings. |
| **3** | **Proficient** | All routes are functional and produce the expected result. | Code is clear and easy to follow. Submitted code does not include TODOs. Nearly all functions have docstrings. |
| **4** | **Advanced** | Stretch challenges are complete and demonstrate an advanced understanding of the concepts presented. | Code is extensible and may utilize helper functions, classes, or advanced data structures to aid in readability. |

## Getting Started

There's quite a lot of setup for this assignment! I've broken it down into a few parts.

### GitHub

If you haven't yet, create a folder to contain your work for this course. If you put it in the `/dev/courses` folder, then the full path would be something like `/dev/courses/web1.1`.

Download the [starter code](https://github.com/Tech-at-DU/ACS-1710-Homework-5-Databases-Starter) and initialize a new git repo.

Refresh the page in your newly-created GitHub repo to make sure your changes were successfully pushed.

### Running a MongoDB Server

Follow the [MongoDB Setup Instructions](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/) to install and run a MongoDB server on your computer.

Install with the command:

```
brew install mongodb-community@8.0
```

And run with the command:

```
brew services start mongodb-community@8.0
```

This will run a MongoDB server on the local URL `localhost:27017`, which will only be reachable from your machine. That's fine for now, because you'll also be running the Flask server on your machine, on `localhost:5000`.

You can stop the MongoDB server with: 

```
brew services stop mongodb-community@8.0
```

### Installing Packages - Virtual Environment

If you'd like, you can use a [Python virtual environment](https://packaging.python.org/guides/installing-using-pip-and-virtual-environments/) for this assignment. This will allow you to install Python packages _only_ for this assignment, so that they won't "pollute" your global environment. If you choose _not_ to do this step, please skip to the "Installing Packages - No Virtual Environment" section.

To create a new virtual environment, navigate to your project's directory, and enter the command:

```bash
python3 -m venv env
```

This will create a folder called `env` within your project directory that will hold a copy of all installed packages. **IMPORTANT: DO NOT SUBMIT YOUR VIRTUAL ENVIRONMENT TO GRADESCOPE.** If you do, it'll freeze the website and I won't be able to grade your work. :-(

Create a new file in the root directory of your project. Name this `.gitignore` (this file name beigns with a dot . ). Copy the text [here](https://raw.githubusercontent.com/github/gitignore/master/Python.gitignore) to that file and save.  

To activate your virtual environment, navigate to your project directory and enter the command:

```bash
source env/bin/activate
```

Once you've activated your virtual environment, enter the following command to install all packages needed for this assignment:

```bash
pip3 install -r requirements.txt
```

When you're finished working on this project, you can deactivate your virtual environment with the command:

```bash
deactivate
```

### Installing Packages - No Virtual Environment

If you choose not to use a virtual environment, simply navigate to your project's directory and enter the following command to install all required packages:

```bash
pip3 install -r requirements.txt
```

## Instructions

### Getting Used to the Codebase

Once you have cloned the starter code, navigate to the project directory and run:

```
python3 app.py
```

to start the server. Open up the site in your local browser, and click around to see what you can do! You should be able to visit the `plants_list`, `about`, `create`, `detail`, and `edit` pages. Read over the code in `app.py` and `templates/` to get a feel for how the code works together to display each page.

### Create a Plant

The first thing to do is to get the create route working! Complete the TODOs in the app's `create()` route, then run the code and try creating a few plants!

Note that this route is a little bit special, as it accepts both a `GET` and a `POST` request, so it is essentially doing double duty. We'll use if/else statements to do something different depending on if the user is viewing the form (`GET`), or submitting the form (`POST`).

**HINT**: If you're having trouble with this step, look at examples of using the [insert_one](https://api.mongodb.com/python/current/api/pymongo/collection.html#pymongo.collection.Collection.insert_one) operation!

When you use `insert_one()` it *returns* a reference to the object that was just created in the database. You can get the id of that object from the `inserted_id` property.  

Use the [Robo 3T program](https://robomongo.org/) to inspect the contents of your database and verify that the data was added.

For the details page to see the plant you just created you need to give it the id of that plant. Every new record created in the Mongo database will be assigned a unique id. **The details page will NOT show the plant details until you tackle that problem below**. You can check that the id is working correctly by looking at the url in the details page, it should read something like: `http://127.0.0.1:5000/plant/673fa679c69ddf9b95e566b3`. The value `673fa679c69ddf9b95e566b3` is a Mongo id. 

### List Plants

Now that we've got a few plants in the database, the next step is to show all plants on the homepage!

Complete the TODOs in the app's `plants_list()` route to get all plants in the database, then complete the TODOs in the `plants_list.html` template to show all plants. Make sure you use a for loop to loop over the list of results!

**HINT**: If you're having trouble with this step, look at examples of using the [find](https://api.mongodb.com/python/current/api/pymongo/collection.html#pymongo.collection.Collection.find) operation!

In your Jinja template you can access the id of a plant with the key `_id`. 

The template creates a listing for each plant in the database. Each listing is in the form of a card that includes:

- An image wrapped in an anchor (link) tag.
- Div with an anchor that shows the name of the plant.

You need to include the `_id` of each plant at the end of the url in the anchor tags (there are two of these).

The name of the plant should be inserted into into the second anchor tag. 

The `img` tag needs to have the photo_url in it's `src` attribute. 

The starter code shows a few plants to mock up what the page should look like. Delete all but one of these and use that one as the starting place for your template. 

See module 5: https://github.com/Tech-at-DU/ACS-1710-Web-Architecture/blob/master/Lessons/module-5/lesson-4.md#read--find-in-pymongo

### Plants Detail

Usually if a website lists many objects, you'll want to have a way to "zoom in" on a single object and see all of its relevant details.

Complete the TODOs in the `detail()` route, as well as in the `detail.html` template, to get the plant with the requested id and pass it to the template, then display its information.

**HINT**: If you're having trouble with this step, look at examples of using the [find_one](https://api.mongodb.com/python/current/api/pymongo/collection.html#pymongo.collection.Collection.find_one) operation!

Looking closely at the details route, you will see that the route receives `plant_id` as a param. This is a string and must be converted to an object id for use with Mongo. Something like: `mongo.db.plants.find_one(ObjectId(plant_id))`.

Fix the `details.html` template by serching through the mockup for relevant elements and replace them with data passed to the template from your route. These are: 

- plant name
- image needs the photo url
- date planted
- variety
- edit url needs the plant id (`_id`)
- harvest form action needs the plant id
- Delete form needs the plant id

### Add a Harvest

Complete the TODOs in the `harvest()` route to process the results of the form on the detail page. Then, modify the `detail.html` page to use a for loop to display all harvests.

### Edit Plant

Note that this route is a little bit special, as it accepts both a `GET` and a `POST` request, so it is essentially doing double duty. We'll use if/else statements to do something different depending on if the user is viewing the form (`GET`), or submitting the form (`POST`).

Complete the TODOs in the `edit()` route to take the results of the form and use them to update the specified plant. If the user is merely viewing the form, we should show that object's current data so that the user knows what they're editing. Complete the rest of the TODOs in the `edit()` route and the `edit.html` template to show the current values of the plant being edited.

**HINT**: If you're having trouble with this step, look at examples of using the [update_one](https://api.mongodb.com/python/current/api/pymongo/collection.html#pymongo.collection.Collection.update_one) operation!

To update a plant use `mongo.db.plants.update_one()`. This method takes search-params and changes. Both are dictionaries, the first describes the object you want to update, and the second contains the properties and values that should be updated in that object. 

The `changes` dictionary should look the same as the `new_plant` in the create route but, you will update the properties with values from the form, get those values from the `request` object. You'll need to wrap this in the another dictionary with one key `$set`. Something like: `{ '$set': updated_plant }`

The search-params should include the `_id` of the plant you are editing. You should take the string `plant_id` and pass that to the `ObjectId()` function to turn it into a Mongo id. 
 
### Delete Plant

Complete the TODOs in the `delete()` route to delete the plant with the given id.

**HINT**: If you're having trouble with this step, look at examples of using the [delete_one](https://api.mongodb.com/python/current/api/pymongo/collection.html#pymongo.collection.Collection.delete_one) operation!

Notice that `delete_one` requires a dictionary with the properties of the record you wish to delete. The id is best to use here becuase it uniquely identifies a record. You might pass something like: `{ '_id': ObjectId(plant_id) }` to `delete_one()`. 

See Module 5: https://github.com/Tech-at-DU/ACS-1710-Web-Architecture/blob/master/Lessons/module-5/lesson-4.md#delete--delete_one-in-pymongo

## Stretch challenges

Stretch challenges are totally up to you! Here are some ideas you may want to consider:

1. **Error Handling**: If the plant with the given `_id` doesn't exist, show a custom 404 page.
1. **Styles Level Up**: Customize the HTML code or `style.css`!
1. **More Resources**: Try adding more resources to the database!

## Submission

When you're ready to submit your work, make sure you push all of your changes to GitHub:

```bash
git add .
git commit -m'Completed all challenges'
git push
```

Then, submit your assignment using [Gradescope](https://gradescope.com).
