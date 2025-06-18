# Introduction to Databases

## 1710 - Module 5: Lesson 1

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Describe Restful Routes
- Explain why a database is useful to a large-scale application.

## What is REST?

**REST** stands for **Representational State Transfer**. It’s a set of rules used to organize how web applications communicate with each other.

Think of REST as a common language that helps different systems talk clearly and consistently over the internet — especially when working with data like users, posts, or weather info.

## REST and Resources

In REST, we treat pieces of data (like a book, a user, or a plant) as **resources**. Each resource has a **URL** (like an address), and we use **HTTP methods** to perform actions on them.

## The 4 Main HTTP Methods

| Method | What it Does | Example                    |
| ------ | ------------ | -------------------------- |
| GET    | Read data    | `GET /books` (list books)  |
| POST   | Create data  | `POST /books` (add book)   |
| PUT    | Update data  | `PUT /books/1` (edit book) |
| DELETE | Remove data  | `DELETE /books/1`          |

## RESTful Routing

**RESTful routing** means using URLs and methods in a consistent and predictable way. For example:

* `GET /plants` → list of plants
* `GET /plants/2` → details for plant with ID 2
* `POST /plants` → create a new plant
* `DELETE /plants/2` → delete plant 2

This style makes it easier to build, understand, and maintain web apps.

# Restful Routes

# RESTful Routing & Naming Best Practices – Worksheet

## Introduction

In web development, a **route** connects a URL to a function in your code. In Flask, routes define how your app responds to different web requests.

RESTful routing is a set of **conventions** that help make your routes clear, predictable, and easy to understand.

Instead of using verbs in your URLs like `/getWeather` or `/createUser`, RESTful routing uses **nouns for resources** (like `/weather`, `/users`) and **HTTP methods** (GET, POST, PUT, DELETE) to describe the actions.

## 📘 Common RESTful Routes

Imagine you’re working with a `plants` resource.

| Action           | Method      | Route                 | Description                      |
| ---------------- | ----------- | --------------------- | -------------------------------- |
| View all plants  | GET         | `/plants`             | Show a list of all plants        |
| View one plant   | GET         | `/plants/<id>`        | Show details about one plant     |
| Create new plant | POST        | `/plants`             | Add a new plant                  |
| Show form to add | GET         | `/plants/new`         | Show a form to create a plant    |
| Edit a plant     | GET         | `/plants/<id>/edit`   | Show a form to edit a plant      |
| Update a plant   | PUT/POST    | `/plants/<id>`        | Save the updated plant data      |
| Delete a plant   | DELETE/POST | `/plants/<id>/delete` | Remove a plant from the database |

## ✨ Naming Tips

* ✅ Use **nouns** for your URLs (e.g., `/weather`, not `/getWeather`)
* ✅ Use **plural** for collections (`/plants`, not `/plant`)
* ❌ Avoid verbs in the route (`/delete-user`) — the HTTP method already tells you the action
* ✅ Use **nested routes** to show relationships (e.g., `/plants/<id>/harvests`)

## 🧪 Practice Examples

Here are some routes. Identify if they follow RESTful naming and suggest improvements if needed.

1. `/getUserInfo`
2. `/posts/123`
3. `/createComment`
4. `/products`
5. `/delete/789`

Answer the RESTful route questions on gradescope!

## Route Names

### 📌 What is REST?

REST stands for **Representational State Transfer**. It’s a set of rules that developers follow when building web applications, especially when dealing with **resources** like users, posts, or plants.

In REST, **the URL represents the resource**, and **the HTTP method (GET, POST, PUT, DELETE)** represents the action.

### 🌱 RESTful Route Naming Basics

Let’s say we’re working with a resource called `plants`.

| Action               | HTTP Method    | Route                 | Description                        |
| -------------------- | -------------- | --------------------- | ---------------------------------- |
| View all plants      | GET            | `/plants`             | Show a list of all plants          |
| View one plant       | GET            | `/plants/<id>`        | Show details about a single plant  |
| Create a new plant   | POST           | `/plants`             | Add a new plant                    |
| Show the create form | GET            | `/plants/new`         | (Optional) Show the form to create |
| Edit a plant (form)  | GET            | `/plants/<id>/edit`   | Show the form to edit a plant      |
| Update a plant       | PUT or POST    | `/plants/<id>`        | Save updates to a plant            |
| Delete a plant       | DELETE or POST | `/plants/<id>/delete` | Remove a plant                     |

### 🔧 Why It Matters

* ✅ **Clear and predictable** — Routes tell you exactly what’s happening.
* ✅ **Easy to maintain** — Follows a common pattern developers understand.
* ✅ **Works well with frontend tools** — Makes connecting APIs and frontend simpler.

### 🧠 Quick Tips

* Use **plural nouns** for collections (`/plants`, not `/plant`).
* Avoid verbs in the route name. Let the **HTTP method do the action**.

  * ❌ `/create-plant`
  * ✅ `POST /plants`
* Use nested routes to show relationships:

  * ✅ `/plants/<id>/harvests` (harvests belong to a plant)

### ✅ Summary

RESTful routes are named using **nouns** to represent the data, and **HTTP methods** to represent what you want to do with that data. This helps keep your web app organized and easy to understand.

# Video Companions 🎥

<!-- [Video 1 - Introducing databases technologies and how they fit into an application](https://file.notion.so/f/f/6004cc36-d69e-461f-a1c5-8e5078ac8f6b/9ad0641a-4b88-4a68-8b15-ec119e08c204/RPReplay_Final1611090729.mp4?table=block&id=f428d7aa-f9d2-4414-992b-72fe01c2fa86&spaceId=6004cc36-d69e-461f-a1c5-8e5078ac8f6b&expirationTimestamp=1728064800000&signature=kJMjO2CCkbc2GBhuTP0nk2zPx-swKaAcvg00lPB1M2s&downloadName=RPReplay_Final1611090729.mp4) -->

[Video 1 - Introducing databases technologies and how they fit into an application](https://youtu.be/2K8eT3VfnuA)

Video 1 - Introducing databases technologies and how they fit into an application

# Exercises 💪

Answer the questions in the `README` file in [](https://repl.it/team/WEB11/Module-51Introduction-to-Databases)[this Repl.it](https://repl.it/team/WebArchitecture/Module-51Introduction-to-Databases) and submit your work.

# Written Companion 🗒

<aside>
🤔 How do we store massive amounts of data in an organized fashion that can also be accessed/modified quickly?

</aside>

---

A technology designed to hold data can be defined as a **database.** Key features of a database include:

- it being a place to store data (i.e. user profiles, website usage, business transactions, etc.)
- typically stores data using **key-value** pairs that exists seperate from a web server
- multiple applications can access its data simultaneously
- stored data can be queried and analyzed efficiently
- data remains stable and non-volatile (aka values don't change in a power outage or application crash)

<aside>
💡 Separating databases from web servers allows each to perform a more specialized function! It also ensures that databases can better serve multiple destinations.

</aside>

A database has many uses, but some of the most commonly use cases include:

- being a location that user data can be easily referenced from
- simple storage
- identifying and understanding the relationships between data

A good analogy for the role a database plays in an application would be what fridges do for a kitchen. A fridge keeps food in a usable state that can be easily accessed!

![untitled.png](Untitled.png)

*Fig 1 - we store food and retrieve food from a fridge in the same fashion we store and retrieve data in a database!*
