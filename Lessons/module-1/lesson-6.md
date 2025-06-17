# Interacting with Form Data in Flask

ACS 1710 - Module 1: Lesson 6

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Write Flask routes that accept either a GET or a POST request.
- Collect form data from a user-submitted form, perform operations on the data, and show the user a result.

## Videos 🎥

<!-- [Vid 1 - Using Flask's request method to work with `<form>` data in routes](https://file.notion.so/f/f/b55c22ee-fac0-43f5-b763-ad205bab0599/61e7d94e-4e14-49d3-aa74-5276af2c144b/6_Forms_and_request_edited.mp4?table=block&id=a9bb8bf6-5597-41e6-a1dd-1d455580e80f&spaceId=b55c22ee-fac0-43f5-b763-ad205bab0599&expirationTimestamp=1728064800000&signature=4QQCMysUohN5q2NJKbzAO7OCWDRoZEhKj13M_pK94RI&downloadName=6_Forms_and_request_edited.mp4) -->

[Vid 1 - Using Flask's request method to work with `<form>` data in routes](https://youtu.be/5KvnErD1YG8)

# Exercises 💪

Answer the review questions for Module 1 Section 5 on [Gradescope](http://gradescope.com).

# Written Companion 🗒

<aside>
🤔 We now know how to create forms and connect them to routes using the `action` property—but how do we interact with the data collected from the `<form>`?

</aside>

`<form>` data can be utilized on the server-side with Flask's built-in `request` function. More specifically, the following two methods of `request` must be invoked for the following two use-cases:

- `request.args.get('inputNameAttribute')` for `GET` requests
- `request.form.get('inputNameAttribute')` for `POST` requests

Do not be confused by the the naming of the `request.form.get()` method! A `<form>` can send information to any type of route. `request.form.get()` must be used to access `<form>` data in POST routes; no more no less. This can be quite confusing unfortunately, so just remember to use args.get() for GET requests and `form.get()` for POST requests.

```html
<!-- a form tag with an action and method attribute added to it -->
<form action="/results" method="GET">
   What's your favorite pizza flavor?
   <input type="text" name="pizza_flavor">
   <input type="submit" value="Submit">
</form>
```

Fig 1 (HTML) - the same <form> from the previous lesson repeated here to keep code consolidated

Once a `<form>` sends information to the route specified in the action attribute, the route can access any `<input>` values using the name attribute of the `<input>` tag.

```python
# a route utilizing the `pizza_flavor` input tag data
@app.route('/results', methods=['GET'])
def simple_pizza_results():
		# NOTE: request.args.get() must be used for GET requests
    pizza_flavor = request.args.get('pizza_flavor')
    return 'You ordered ' + pizza_flavor + ' pizza!'
```

*Fig 2 (Python) - a `GET` route utilizing `request.args.get()` to collect information from the `<input name="pizza_flavor">` tag*

Changing the `method` attribute of the `<form>` tag to use `POST` would require using the `request.form.get()` approach.

```python
# the same route again but now with the POST method
# NOTE: methods has been changed to use POST
@app.route('/results', methods=['POST'])
def simple_pizza_results():
		# NOTE: request.forms.get() must be used for POST requests
    pizza_flavor = request.form.get('pizza_flavor')
    return 'You ordered ' + pizza_flavor + ' pizza!'
```

*Fig 3 (Python) - a `POST` route utilizing `request.form.get()` to collect information from the `<input name="pizza_flavor">` tag*

- *Note: the `methods` parameter of `app.route` uses an array that can contain multiple `HTTP` methods*
    - *ex: `methods=['GET', 'POST']`*
