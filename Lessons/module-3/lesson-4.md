# Returning JSON Responses with `jsonify`

## ACS 1710 - Module 3: Lesson 4

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Return a JSON response from a Flask route using `jsonify`
- Return an appropriate HTTP status code alongside a Flask route's response

# Exercises 💪

Test your understanding of `jsonify` and status codes with the questions below. Try to answer each one yourself before checking the answer key.

1. What does `jsonify()` do to a Python dictionary?
2. What HTTP status code should a route return after successfully **creating** a new resource? What about a successful `GET` request?
3. How do you return both a JSON response and a custom status code from a Flask route?
4. `str(my_dict)` and `jsonify(my_dict)` can look similar when printed — why aren't they the same thing?

<details>
<summary>Answer Key</summary>

1. It converts a Python dictionary (or list) into a properly-formatted JSON HTTP response, and sets the response's `Content-Type` header to `application/json`.
2. `201 Created` after creating a new resource; `200 OK` for a successful `GET` request.
3. Return a tuple of `(response, status_code)`: `return jsonify(data), status_code` — e.g. `return jsonify(new_plant), 201`.
4. `str(my_dict)` just converts the dictionary to a plain string (using Python's own formatting, like single-quoted keys) with a `Content-Type` of `text/html`. `jsonify()` produces real JSON syntax with the correct `Content-Type: application/json` header, which is what lets another program reliably parse the response as data instead of as plain text.

</details>

# Written Companion 🗒

<aside>
🤔 So far, every route in this course has returned a plain string. That's fine for a page a human reads in a browser—but if another program (a JavaScript frontend, a mobile app, or someone else's server) is calling your route, it needs the data back in a predictable, structured format. How do we return real, well-formed JSON from a Flask route?
</aside>

---

Flask provides a function called `jsonify()` for exactly this purpose. It takes a Python dictionary (or list) and converts it into a proper JSON HTTP response—including setting the `Content-Type: application/json` header, which tells whatever is receiving the response "this is JSON, parse it accordingly."

```python
from flask import Flask, jsonify

app = Flask(__name__)

@app.route('/joke')
def make_joke():
    joke_text = "Chuck Norris can binary search unsorted data."
    return jsonify({'joke': joke_text})
```

*Fig 1 - returning a JSON response using `jsonify()`, instead of a plain string*

<aside>
🚨 It's tempting to just build the string yourself, like <code>return str({'joke': joke_text})</code>. Don't! That returns text that merely <i>looks like</i> JSON, with the wrong <code>Content-Type</code> header attached. A program trying to parse it as JSON may fail, even though it looks fine in a browser.
</aside>

### Returning Status Codes

A response can also include an **HTTP status code** to tell the client how the request went (see Module 1's introduction to status codes for a refresher on `200`, `404`, and `500`). By default, Flask routes return a status code of `200`—but when an API creates, updates, or fails to find a resource, it should say so explicitly.

To do this, return a **tuple** of `(response, status_code)` from your route:

```python
@app.route('/plants', methods=['POST'])
def create_plant():
    new_plant = {
        'name': request.form.get('name'),
        'variety': request.form.get('variety')
    }
    # ... code to insert new_plant into the database would go here ...

    return jsonify(new_plant), 201
```

*Fig 2 - returning a `201 Created` status code alongside the newly-created resource*

Some of the most common status codes used in APIs:

- `200` = OK — the request succeeded (the default for `GET` requests)
- `201` = Created — a new resource was successfully created (common after a `POST` request)
- `400` = Bad Request — the client sent invalid or malformed data
- `404` = Not Found — the requested resource doesn't exist
- `500` = Internal Server Error — something went wrong on the server's end

<aside>
💡 Recent versions of Flask will actually convert a dictionary returned directly from a route (e.g. <code>return new_plant</code>) into JSON automatically. Using <code>jsonify()</code> explicitly is still the clearest, most common approach—especially once you need to pair your data with a status code.
</aside>
