# Introduction to the Request/Response Cycle

ACS 1710 - Module 1: Lesson 1 

## Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Explain how websites use the Request-Response Cycle to receive user input and show content to the user
- Identify the "request" and the "response" for a given web page

## Videos 🎥

<!-- [Vid 1 - Breaking down the Request/Response Cycle with Meow.io](https://file.notion.so/f/f/b55c22ee-fac0-43f5-b763-ad205bab0599/0bcfbd95-79ed-4184-b36c-d849beb3a4ce/RPReplay_Final1610465677.mp4?table=block&id=190f592a-ef75-45db-bb74-cc8f313e8a7c&spaceId=b55c22ee-fac0-43f5-b763-ad205bab0599&expirationTimestamp=1728064800000&signature=_G9gV-hTHvHCk7LXVmYFFYSUOiFhJ1jWnj3uBy40rZc&downloadName=RPReplay_Final1610465677.mp4) -->

[Vid 1 - Breaking down the Request/Response Cycle with Meow.io](https://youtu.be/2CYu4d0-YJk)

## Exercises 💪

Test your understanding of the Request/Response Cycle with the questions below. Try to answer each one yourself before checking the answer key.

1. In the mail-order catalogue example from this lesson, who plays the role of the **client**, and who plays the role of the **server**?
2. Which side of a web communication always **starts** the exchange — the client or the server?
3. A user types `www.example.com` into their browser and a page loads. Which part of this interaction is the **request**, and which part is the **response**?
4. What does a status code of `200` mean? What about `404`? What about `500`?
5. True or False: A server can skip sending a response if the client's request doesn't need any data back.

<details>
<summary>Answer Key</summary>

1. The **buyer** is the client (they start the communication); the **seller** is the server (they reply to the communication).
2. The **client** always starts the exchange by sending a request.
3. The **request** is the browser asking the server at `www.example.com` for the page; the **response** is the data the server sends back that the browser uses to display the page.
4. `200` = OK, the request succeeded. `404` = the server (or resource) could not be found. `500` = the server failed to execute the request.
5. **False** — a server must always send back a response, even if it's just a success/fail status code with no other data.

</details>

## Written Companion 🗒

How do devices on the internet communicate with each other and how can we build applications that use that same pattern?

Before we look at online communication, let's consider how traditional mail delivery works. For this example we can assume that a buyer would like to purchase something from a mail order catalogue:

1. The buyer fills out a physical form with the details of the items they'd like to purchase and includes a check for the required amount (made out to the seller)
2. The buyer places the form and the checks in an envelope, then mails it out to the address of the seller (this gets delivered to the seller by a mail courier such as UPS)
3. The seller receives the envelope from the mail delivery service. They open up the envelope, checks what items the buyer would like to purchase and if the given money covers the purchase, and puts all the items in a box to be sent back.
4. The seller sends the box via the same mail courier and the buyer gets their items.

Online communications follow this same pattern! We call the machine starting the communication (i.e. the buyer in the above example) the client and the machine that replies to the communication (i.e. the seller from above) as the server.

Clients always start the communication by creating a request and sending it to the server.

![request-response.png](request-response.png)

Clients can discover servers by their destination URL address in the same way that physical mail gets sent to a physical destination address (such as 555 Post Street, San Francisco, CA). We refer to this destination URL address as a route.

Notice in Fig 1.1 that the client sends a request to the server via the server's route: www.pinterest.com.

The server always ends the communication by creating a response and returning it to the client.

![module-1-lesson-1-2.png](module-1-lesson-1-2.png)

Once the client receives the response from the server—communication ends and the client must make a new request to for further interactions. Every communication will follow this loop!

Regardless of what the request by the client contains (for example, it could be a request to store an image) the server must always return a response! Even if that response contains nothing more than a success/fail status code.

A **response** includes a numerical status code. Some common status codes include:

- 200 = OK - successful execution of the request
- 404 = Server not found
- 500 = Server failed to execute the request
