# GET vs POST

ACS 1710 - Module 1: Lesson 4

## Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Explain the differences between GET and POST requests.
- For a given example of a request, identify whether it should be a GET or POST request.

## Videos 🎥

<!-- [Vid 1 - Exploring applications and differences between the HTTP GET and POST and methods via Grumble.io](https://file.notion.so/f/f/b55c22ee-fac0-43f5-b763-ad205bab0599/8cc1a9e1-4326-4ca2-8372-a97cf16e3ed9/get_vs_post_take2.mov?table=block&id=fcce6099-1999-4356-800a-db640da1a49d&spaceId=b55c22ee-fac0-43f5-b763-ad205bab0599&expirationTimestamp=1728064800000&signature=0570wwmoAnOApx5JuKfQN9asQxsAvvdmRLeHVFIq3v8&downloadName=get_vs_post_take2.mov) -->

[Vid 1 - Exploring applications and differences between the HTTP GET and POST and methods via Grumble.io](https://youtu.be/jjwQQGIR1RU)

## Exercises 💪

Test your understanding of GET vs POST with the questions below. Try to answer each one yourself before checking the answer key.

1. Which HTTP method is used to **retrieve** data from a server, and which is used to **send** data to a server?
2. True or False: Data sent via a `GET` request can be seen in the URL.
3. A user submits a login form with their username and password. Should this be a `GET` or `POST` request? Why?
4. A user searches for "pizza" in a search bar and the results page shows `?query=pizza` in the URL. Was this form submitted using `GET` or `POST`?
5. Which C.R.U.D. operation is most closely associated with the `GET` method?

<details>
<summary>Answer Key</summary>

1. `GET` retrieves/receives data from the server; `POST` sends data to the server.
2. **True** — `GET` request data is visible in the URL.
3. `POST` — sensitive data like a password shouldn't be visible in the URL, which is what a `GET` request would do.
4. `GET` — the query is visible in the URL, which only happens with `GET` requests.
5. **Read** — `GET` is typically used whenever the user needs to read data.

</details>

## Written Companion 🗒

Sometimes we want to receive data, while other times we want to send data. How do we differentiate between these two different types of requests?

Clients can create many types of requests. 

Try to imagine some of the user situations in which different requests might get made. For example, perhaps the user wants to get a list of shopping items from a website—while other times the user wants to upload their item for sale.

In this article, we will be exploring the two most common request methods — GET and POST.

The GET method provides data to the client, from the server, while the POST method provides data from the client, to the server. 

### Summary of the HTTP GET Method

- Used to make requests for **receiving** data.
- User data can be visibly seen in the URL when using `GET`

Examples:

- making a search query to a database
- sending a simple confirmation message

### Summary of the HTTP  POST Method

- Used to make requests geared towards **sending data** to be utilized as resource—usually to change the state of a system
- Form data can not be visibly seen in the URL

Examples:

- sending a username/password information to a sign-in portal
- updating a users profile information (i.e. adding a phone number or changing an account's email)

### GET and POST in relation to C.R.U.D

When the user needs to **read** data—`GET` should typically be employed.

**Creating, updating, and deleting** operations traditionally utilized the `POST` method. However, other HTTP methods have emerged such as `PUT` (for updating) and `DELETE` (for deleting)—leaving `POST` as the go-to for creation operations.
