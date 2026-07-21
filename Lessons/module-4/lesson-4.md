# Testing Flask Routes with Pytest

## ACS 1710 - Module 4: Lesson 4

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Use Flask's test client to simulate requests to your routes from a test file.
- Write a Pytest test that verifies a Flask route returns the expected status code and content.

# Exercises 💪

Test your understanding of testing Flask routes with the questions below. Try to answer each one yourself before checking the answer key.

1. What Flask object or method lets you send simulated requests to your app in a test, without starting a live server?
2. What naming convention do test files and test functions typically follow so that Pytest can automatically discover and run them?
3. Given `result = client.get('/')`, how would you assert that the response was successful?
4. `result.data` returns bytes, not a string (e.g. `b'Hello, world!'`). Write an assertion that checks whether the word `"Hello"` appears anywhere in the response, without needing an exact match.
5. How would you simulate a `POST` request that submits `flavor=mango` as form data to `/froyo_results`?

<details>
<summary>Answer Key</summary>

1. `app.test_client()` — it creates a Flask test client that can send simulated requests directly to your app.
2. Test files are named `test_*.py`, and the test functions inside them are named `test_*` — Pytest automatically discovers and runs anything matching this pattern.
3. `assert result.status_code == 200`
4. `assert b'Hello' in result.data`
5. `client.post('/froyo_results', data={'flavor': 'mango'})`

</details>

# Written Companion 🗒

> 🤔 How do we know our routes actually work, without opening a browser and clicking through the whole application by hand every time we make a change?

---

Manually testing a route—opening the browser, navigating to a URL, checking that the output looks right—works fine the first time. But it doesn't scale: every time you change your code, you'd need to re-click through your entire application to make sure nothing broke. It's also easy to forget to check something.

> 💡 An automated test lets you verify your app still works correctly with a single command, run in seconds, every time you make a change.

In this class, we'll use **Pytest**, a widely-used Python testing library, along with Flask's built-in **test client**. The test client lets a test simulate a request to one of your routes—without actually starting a live server or opening a browser.

### Writing a Test File

Pytest automatically discovers tests that follow a naming convention: test files are named `test_*.py`, and individual test functions inside them are named `test_*`. Each test uses Python's `assert` statement to check that something is true; if the assertion fails, Pytest reports that test as failed.

```python
# app.py
from flask import Flask

app = Flask(__name__)

@app.route('/')
def homepage():
    return 'Hello, world!'

@app.route('/animal/<users_animal>')
def favorite_animal(users_animal):
    return f'Wow, {users_animal} is my favorite animal, too!'

if __name__ == '__main__':
    app.run(debug=True)
```

*Fig 1 - a simple `app.py` with two routes to test*

```python
# test_app.py
from app import app

def test_homepage():
    client = app.test_client()
    result = client.get('/')

    assert result.status_code == 200
    assert result.data == b'Hello, world!'

def test_favorite_animal():
    client = app.test_client()
    result = client.get('/animal/zebra')

    assert result.status_code == 200
    assert b'zebra' in result.data
```

*Fig 2 - a `test_app.py` file with two tests, one per route*

- *Note: `result.data` returns the response body as raw **bytes**, not a regular string—that's why it's compared against `b'Hello, world!'` (with a `b` prefix) instead of `'Hello, world!'`. The `in` keyword works on bytes too, which is handy when you only want to check that a route's response *contains* something, rather than match it exactly.*

Run all of your tests from the terminal with:

```bash
pytest
```

Or run just one test by name:

```bash
pytest -k 'test_favorite_animal'
```

### Testing Routes That Accept Form Data

The test client can also simulate a `POST` request with form data, using the same `data=` dictionary syntax you'd expect from an actual `<form>` submission:

```python
def test_froyo_results():
    client = app.test_client()
    result = client.post('/froyo_results', data={'flavor': 'mango'})

    assert result.status_code == 200
    assert b'mango' in result.data
```

*Fig 3 - simulating a `POST` request with form data, then checking that the submitted value shows up in the response*

> 💡 This is the same testing approach used in this module's graded assignment—so the tests you write there should look a lot like the examples above!
