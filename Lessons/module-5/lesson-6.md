# Deploying Your Flask Application

## ACS 1710 - Module 5: Lesson 6

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Deploy a Flask application with a live database connection to a hosting provider.

# Exercises 💪

Test your understanding of deployment with the questions below. Try to answer each one yourself before checking the answer key.

1. Why can't a deployed app connect to `mongodb://localhost:27017`, even though that URI works fine when you run your app on your own computer?
2. What's the purpose of a WSGI server like `gunicorn`, and why isn't Flask's built-in development server (`app.run()`) good enough for production?
3. Where should your database's username and password live once you deploy—hardcoded into `app.py`, or set as environment variables on the hosting platform? Why?
4. If your deployed site shows an error page, what's the first thing you should check?

<details>
<summary>Answer Key</summary>

1. `localhost` means "this same machine." On your computer, that's your computer—but on the hosting provider's servers, `localhost` refers to their own remote machine, which doesn't have your local MongoDB installation running on it. You need a database reachable over the internet, like a MongoDB Atlas cluster.
2. `gunicorn` is a production-ready, multi-threaded web server that can handle multiple simultaneous requests efficiently. Flask's built-in server is single-threaded and explicitly meant only for local development, not for serving real user traffic.
3. As environment variables set on the hosting platform. Hardcoding secrets into `app.py` means anyone who can see your code (e.g. on GitHub) can see your database password.
4. Your host's deployment logs — they'll usually show you the exact error (a missing dependency, a connection failure, a typo, etc.) that's causing the site not to load.

</details>

# Written Companion 🗒

> 🤔 You've built a Flask app that runs on your computer—how do you get it running on a real URL that anyone on the internet can visit?

---

Congratulations—you've built (several!) working Flask applications. The last step is **deployment**: getting your app running on a server that's reachable from anywhere, not just `localhost` on your own machine.

We'll use [Render](https://render.com), a hosting provider with a free tier for web services that doesn't require a credit card to get started.

## Before You Start

A couple of terms we'll use throughout this lesson:

- **Repository** — your project's GitHub repo. Render deploys directly from GitHub, so your code needs to be pushed there first.
- **Web Service** — Render's term for a deployed backend application, as opposed to a static site.

## Step 1: Install Gunicorn

Render (like most hosting providers) doesn't run your app with Flask's built-in development server (`app.run()`)—that server is single-threaded and meant only for local development. Instead, we'll use **gunicorn**, a production-ready WSGI server that can handle multiple requests at once.

If you're using a virtual environment, activate it, then run:

```bash
pip3 install gunicorn
pip3 freeze > requirements.txt
```

This installs `gunicorn` and adds it to your `requirements.txt` file, so Render knows to install it too.

## Step 2: Push Your Code to GitHub

Make sure your latest code—including the updated `requirements.txt`—is committed and pushed to GitHub:

```bash
git add .
git commit -m 'Prepare for deployment'
git push
```

## Step 3: Create a Web Service on Render

1. Sign up for a free account at [render.com](https://render.com).
2. From your dashboard, click **New +** → **Web Service**.
3. Connect your GitHub account, and select the repository for your project.
4. Configure your service:
   - **Runtime**: `Python 3`
   - **Build Command**: `pip install -r requirements.txt`
   - **Start Command**: `gunicorn app:app` (replace `app` with the name of your main Python file, without the `.py`)
5. Click **Create Web Service**.

Render will start building and deploying your app. This can take a few minutes—and just like the first time you ran a local server, **things rarely work perfectly on the first try**! Let's debug.

## Step 4: Read the Logs

If your app fails to deploy, or the live site shows an error, click the **Logs** tab in your Render dashboard. This shows you exactly what went wrong—usually a missing dependency, a typo, or (most likely, for us) a database connection problem.

## Step 5: Connect to a Production Database with MongoDB Atlas

If your local app connects to MongoDB using `mongodb://localhost:27017`, that will **not** work once deployed—`localhost` refers to "this same machine," and Render's servers don't have your local MongoDB installation running on them. You need a database that's reachable over the internet: **MongoDB Atlas**.

If you haven't yet, follow the steps in [this tutorial](https://docs.atlas.mongodb.com/getting-started/) to set up a free MongoDB Atlas cluster, and create a database user with a username & password.

From the Atlas dashboard, go to your cluster's **Connect** page, then **Connect your application**:

<img src="atlas-connect.png" width="100%">

Select the `Python` driver, choose a recent version, and check the box for `Include full driver code example`. Then click **Copy** to copy the code:

<img src="atlas-copy-code.png" width="80%">

Paste that into your application's `app.py` file, replacing any existing database setup code. Make sure to swap in your actual username, password, and database name. Your connection code should look something like:

```py
import os
from pymongo import MongoClient
from dotenv import load_dotenv

# Set up environment variables & constants
load_dotenv()
MONGODB_USERNAME = os.getenv('MONGODB_USERNAME')
MONGODB_PASSWORD = os.getenv('MONGODB_PASSWORD')
MONGODB_DBNAME = 'mydb'

app = Flask(__name__)

client = MongoClient(f"mongodb+srv://{MONGODB_USERNAME}:{MONGODB_PASSWORD}@cluster0.idqxn.mongodb.net/{MONGODB_DBNAME}?retryWrites=true&w=majority")
db = client[MONGODB_DBNAME]
```

*Fig 1 - connecting to a MongoDB Atlas cluster using environment variables for the username and password*

Add your database user's credentials to your local `.env` file (see Module 4's lesson on `dotenv` for a refresher):

```
MONGODB_USERNAME=yourusernamegoeshere
MONGODB_PASSWORD=yourpasswordgoeshere
```

You'll also need to add `pymongo`, `python-dotenv`, and `dnspython` to your `requirements.txt` file.

> 🚨 Never commit your `.env` file to GitHub—it should already be listed in your `.gitignore`. Your database credentials should never end up in a public repository!

## Step 6: Set Environment Variables on Render

Since `.env` isn't committed to GitHub, Render never sees it—so your deployed app needs its own copy of these environment variables. In your Render dashboard, go to your web service's **Environment** tab and add:

- `MONGODB_USERNAME` = your database username
- `MONGODB_PASSWORD` = your database password

Save your changes—Render will automatically redeploy your app with the new environment variables available.

## If Your Deployment Was Successful...

You did it! You have a real, live URL running a Flask app with a working database connection—the same skills used to build and ship production web applications.

> 💡 Render's free tier "spins down" a web service after a period of inactivity, so the first request after some idle time may take up to a minute to respond while it spins back up. This is a free-tier limitation only—paid tiers stay running continuously.
