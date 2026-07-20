# RESTful Routing & Naming Conventions

## ACS 1710 - Module 5: Lesson 2

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Describe what RESTful routing is and why it's used.
- Identify whether a given route follows RESTful naming conventions, and suggest an improvement if it doesn't.

# Exercises 💪

Here are some routes. Identify whether each one follows RESTful naming conventions, and suggest an improvement if it doesn't. Try to answer each one yourself before checking the answer key.

1. `/getUserInfo`
2. `/posts/123`
3. `/createComment`
4. `/products`
5. `/delete/789`

<details>
<summary>Answer Key</summary>

1. `/getUserInfo` — **Not RESTful.** It uses a verb in the URL. A RESTful version would be something like `GET /users/<id>`.
2. `/posts/123` — **RESTful.** A plural noun (`posts`) with an ID, typically paired with `GET` to view a single post's details.
3. `/createComment` — **Not RESTful.** It uses a verb in the URL. A RESTful version would be `POST /comments`.
4. `/products` — **RESTful.** A plural noun representing the whole collection, typically paired with `GET` to list all products (or `POST` to create one).
5. `/delete/789` — **Not RESTful.** It uses a verb and doesn't name the resource. A RESTful version would be something like `DELETE /products/789`.

</details>

# Written Companion 🗒

<aside>
🤔 If an API gives a developer a route to interface with data, what's a predictable, consistent way to name and organize those routes?
</aside>

---

## What is REST?

**REST** (Representational State Transfer) is a set of conventions for organizing how web applications communicate with each other. Think of it as a common language that helps different systems talk clearly and consistently over the internet—especially when working with data like users, posts, or plants.

In REST, we treat pieces of data (like a book, a user, or a plant) as **resources**. Each resource has a **URL** (like an address), and we use **HTTP methods** to perform actions on it. The URL represents *what* resource you're working with; the HTTP method represents *what action* you want to take.

### The 4 Main HTTP Methods

| Method | What it Does | Example                      |
| ------ | ------------- | ----------------------------- |
| GET    | Read data     | `GET /books` (list books)     |
| POST   | Create data   | `POST /books` (add a book)    |
| PUT    | Update data   | `PUT /books/1` (edit a book)  |
| DELETE | Remove data   | `DELETE /books/1`             |

## RESTful Routing

**RESTful routing** means using URLs and HTTP methods together in a consistent, predictable way, instead of describing the action inside the URL itself. Imagine you're working with a `plants` resource:

| Action                | Method         | Route                 | Description                       |
| ---------------------- | -------------- | ---------------------- | ----------------------------------- |
| View all plants        | GET            | `/plants`             | Show a list of all plants          |
| View one plant         | GET            | `/plants/<id>`        | Show details about a single plant  |
| Show the create form   | GET            | `/plants/new`         | Show a form to create a plant      |
| Create a new plant     | POST           | `/plants`             | Add a new plant                    |
| Show the edit form     | GET            | `/plants/<id>/edit`   | Show a form to edit a plant        |
| Update a plant         | PUT or POST    | `/plants/<id>`        | Save updates to a plant            |
| Delete a plant         | DELETE or POST | `/plants/<id>/delete` | Remove a plant                     |

This style makes it easier to build, understand, and maintain web apps—anyone familiar with REST conventions can guess what a route does just by reading its method and URL, without needing to read the underlying code.

## Naming Tips

- ✅ Use **nouns** for your URLs (e.g., `/weather`, not `/getWeather`)
- ✅ Use **plural nouns** for collections (`/plants`, not `/plant`)
- ❌ Avoid verbs in the route (`/delete-user`) — the HTTP method already tells you the action
- ✅ Use **nested routes** to show relationships (e.g., `/plants/<id>/harvests`, since harvests belong to a plant)

## Why It Matters

- **Clear and predictable** — routes tell you exactly what's happening.
- **Easy to maintain** — follows a common pattern developers already understand.
- **Works well with frontend tools** — makes connecting APIs and frontends simpler.

<aside>
💡 RESTful routes are named using nouns to represent the data, and HTTP methods to represent what you want to do with that data. Keep this pattern in mind for every route you write from here on!
</aside>
