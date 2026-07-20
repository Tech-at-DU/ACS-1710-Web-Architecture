# Using the Requests Library to Generate User Requests

## ACS 1710 - Module 3: Lesson 6

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Use the Python `requests` library to make simple API requests and display the response.
- Create Flask routes which make API calls and show the user a response.

# Videos 🎥

<!-- [Vid 1 - walking through how to create requests via the `Requests` Python library](https://file.notion.so/f/f/6004cc36-d69e-461f-a1c5-8e5078ac8f6b/9b7579b7-c564-4bee-be36-0dbd4352a7bf/14_Requests_Library.mov?table=block&id=343d29d7-c8f8-4030-853e-a5a93ec86997&spaceId=6004cc36-d69e-461f-a1c5-8e5078ac8f6b&expirationTimestamp=1728064800000&signature=RkqEevW6I5D-wzN-gsBB5xvtBQQ0MtlNsZbbi1Q2rjA&downloadName=14_Requests_Library.mov) -->

[Vid 1 - walking through how to create requests via the `Requests` Python library](https://youtu.be/sJOmt33lq4E)

# Exercises 💪

Test your understanding of the `requests` library with the questions below. Try to answer each one yourself before checking the answer key.

1. Which `requests` library method is used to create a `GET` request, and what are its two main arguments?
2. After calling `requests.get(...)`, what method do you call on the result to extract the JSON payload as a Python dictionary?
3. If an API's response is plain text instead of JSON, what would you use instead of `.json()`?
4. What does it mean for a Flask route to act as an "intermediary" between the user and another API?

<details>
<summary>Answer Key</summary>

1. `requests.get(routeURL, params)` — `routeURL` is the destination URL string, and `params` is a dictionary of key-value pairs for the query parameters.
2. `.json()`, e.g. `result.json()`.
3. `.text` (no parentheses), e.g. `result.text`.
4. The Flask route receives a request from the user, makes its own request to another API, cleans up/processes that API's response, and returns the cleaned-up result back to the user as its own response — the user never talks to the other API directly.

</details>

# Written Companion 🗒

<aside>
🤔 We can use tools like Postman to quickly make requests for API testing, but how do we create a request in Python?

</aside>

---

When developing in a Python environement, the `Requests` library can be used to create requests. The `Requests` library provides us with the following tools:

- `requests.get(routeURL, params)` = the `Requests` method used to create a `GET` request
    - `routeURL` = a string with the route URL information required to find the desired server
    - `params` = an object of **key-value** pairs that contains the query parameters of the search.

The results of a `requests.get()` method includes information such as the header, packet data, and payload. Typically, an application only needs the payload data (most commonly a `JSON` object) so developers will usually use the `.json()` method on the results to seperate the valuable information from the junk.

```python
import requests

# an object containing all the key-value pairs relevant to the query
params = { "category": "dev" } 

# result contains the respone recieved from the requests.get() method
result = requests.get(
    "https://api.chucknorris.io/jokes/random", 
    params=params) 

# strip the JSON data from the results for easier access
joke_json = result.json() 
```

*Fig 1 - a standard request using the requests library to the `[api.chucknorris.io/jokes/random](https://api.chucknorris.io/jokes/random)` API.*

<aside>
🚨 Although less common, a payload may contain data in a raw `.txt` format instead of a `json` object! To work with a `.txt` payload—use `result.text` (notice that `text` intentionally does not have parentheses).
</aside>

---

### Implementing a request into a Flask route

<aside>
💡 Requests can be combined with Flask routes for a variety of results!
</aside>

<aside>
🤔 What happens when we take the results of a `request.get()` query and return it as the output of a Flask route?
</aside>

```python
# the same request snippet from above combined with Flask
import requests
from flask import Flask

app = Flask(__name__)

@app.route('/joke')
def make_joke():
    params = { "category": "dev" }
    result = requests.get( 
        "https://api.chucknorris.io/jokes/random", 
				params=params)
    joke_json = result.json() 

		# users want the contents of the JSON object,
		# not the JSON object itself
    return joke_json["value"]
```

*Fig 2 - Returning the `JSON` contents of the joke to the user when they request information from the `/joke` Flask route*

- *Note: the `/joke` itself route creates a request and recieves a response, then cleans up that data and returns it as a response to the user that queried `/joke`*

<aside>
💡 Combining requests with Flask routes creates an intermediary step for users! They request information from the Flask route, the Flask route requests data from another service and cleans it up, then returns that data as another response.
</aside>

![Fig 3 - An image representing how intermediary steps get leveraged](Untitled-3.png)

Fig 3 - An image representing how intermediary steps get leveraged
