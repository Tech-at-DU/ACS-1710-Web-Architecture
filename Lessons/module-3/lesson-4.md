# Testing API Routes with Postman

## ACS 1710 - Module 3: Lesson 4

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Use the Postman desktop application to make simple API requests.
- Explain how the Postman application is useful for testing out an API.

# Video Companions 🎥

<!-- [Vid 1 - Using Postman to test Flask routes](https://file.notion.so/f/f/6004cc36-d69e-461f-a1c5-8e5078ac8f6b/53801a21-a6bb-4f3a-b84b-a4231ceb0b4a/13_Postman.mov?table=block&id=8a97c6d2-9437-43a5-8cfe-744336be2ffb&spaceId=6004cc36-d69e-461f-a1c5-8e5078ac8f6b&expirationTimestamp=1728064800000&signature=7j9P9J8_LjDR7uAjumYv9q20tHin5uj_nSYq1QLhYBI&downloadName=13_Postman.mov) -->

[Vid 1 - Using Postman to test Flask routes](https://youtu.be/dzdKkd_as7o)

# Exercises 💪

1. Download the [Postman desktop application](https://learning.postman.com/docs/getting-started/installation-and-updates/#installing-postman-on-mac). 
2. Make a query to the Chuck Norris Joke API by using the [API Documentation Page here](https://api.chucknorris.io). Make sure it sends you a response back containing a joke!
3. Send a screenshot of your request to your instructor.

# Written Companion 🗒

<aside>
🤔 What tools can we use to experiment with API's and confirm they work as expected from the user end?

</aside>

---

Once a API route has been created, it should always be tested in a development environment before rolling out to production. Many tools and techniques exist to test an API quickly—but in this class we will be using a tool called **Postman**.

Similar to an internet browser, Postman allows developers to make requests and recieve respones. Postman provides additional tools on top of the traditional intenet browser such as the ability to quickly shape the method of request (`GET`, `POST`, etc.), the query parameters of the request, and request tracing for easier debugging.

![Fig 1 - A `GET` request being sent to *[api.icndb.com/jokes](http://api.icndb.com/jokes)* with one query parameter](Untitled-2.png)

Fig 1 - A `GET` request being sent to *[api.icndb.com/jokes](https://api.chucknorris.io)* with one query parameter
