# Introduction to APIs

## ACS 1710 - Module 3: Lesson 1

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Explain how APIs allow us to leverage third-party data when developing an application.
- Explain how an API receives a request, connects to a database, and sends data back to the client.

# Videos 🎥

<!-- [Vid 1 - Exploring the nature of API's via Gincord.io](https://file.notion.so/f/f/6004cc36-d69e-461f-a1c5-8e5078ac8f6b/9f0481bd-104b-4105-9479-d253291931ab/RPReplay_Final1610466811.mp4?table=block&id=57d33dcb-fe3d-47f6-ba64-037eda1e70b6&spaceId=6004cc36-d69e-461f-a1c5-8e5078ac8f6b&expirationTimestamp=1728064800000&signature=Uc7NyScdTsdeBgC_mgrA-YcA1KzxAX8ytBBSR9OZtRU&downloadName=RPReplay_Final1610466811.mp4) -->

[Vid 1 - Exploring the nature of API's via Gincord.io](https://youtu.be/zXOMHpTOpJM)

# Exercises 💪

Test your understanding of APIs with the questions below. Try to answer each one yourself before checking the answer key.

1. What does the acronym API stand for?
2. In your own words, what is an API?
3. Name two examples of data a company might expose to other developers through an API.

<details>
<summary>Answer Key</summary>

1. Application Programming Interface.
2. A server route that lets developers request and receive data from another company's or service's database, without needing direct access to that database.
3. Answers will vary — examples include transit data, weather data, song lyrics, payment processing, or social media posts.

</details>

# Written Companion 🗒

> 🤔 How do we leverage existing data collected by other services such as Twitter, ESPN, and Uber in our own applications?

---

Companies of all types collect and utilize data on their users. This can range from medical data at a hospital, transport data from a public transit organization, or personalized profile data from a tech company.

This data can be leveraged across platforms and easily shared using an **Application Programming Interface** **(API)**. Developers granted an API permission can tap into another company's data for their own application! 

![Fig 1 - A user requesting `song_lyrics` through an API to get data about songs from another companies database, and that data be returned as a response](Untitled.png)

Fig 1 - A user requesting `song_lyrics` through an API to get data about songs from another companies database, and that data be returned as a response

> 💡 An API is nothing more then a server route which returns information from as a database as a response!
