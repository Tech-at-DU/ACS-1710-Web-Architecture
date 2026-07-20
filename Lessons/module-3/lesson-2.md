# C.R.U.D in API's

## ACS 1710 - Module 3: Lesson 2

<aside>
🤔 If an API provides a developer a **route** to **interface** with another platform—what operations can be performed through this**?**

</aside>

---

<aside>
💡 C.R.U.D operations work their way into just about every aspect of web applications! Including the way developers interact with other platforms/services.
</aside>

Let's breakdown some examples of how C.R.U.D manifests in API's:

- create - using the Twitter API to draft and send a Tweet in an application other than Twitter
- read - retrieving the current number of trains operating via the BART API
- update - Stripe payment plugins that allow payments to be sent directly from a web application to a bank account
- delete - censor bots capable of detecting (i.e. **reading**) and removing posts on Facebook that break the terms and conditions of usage

# Exercises 💪

Test your understanding of C.R.U.D in APIs with the questions below. Try to answer each one yourself before checking the answer key.

1. Match each example to a C.R.U.D. operation: sending a Tweet via the Twitter API, retrieving live train data via the BART API, processing a payment via a Stripe plugin, removing a policy-violating post via a moderation bot.
2. Which C.R.U.D. operation is being performed when an app queries a weather API to display today's forecast?
3. True or False: An API can only be used to read data, never to create, update, or delete it.

<details>
<summary>Answer Key</summary>

1. Twitter API → Create; BART API → Read; Stripe plugin → Update; moderation bot → Delete.
2. **Read** — the app is retrieving existing data from the weather service.
3. **False** — many APIs (like Twitter's or Stripe's) support create, update, and delete operations, not just reading.

</details>