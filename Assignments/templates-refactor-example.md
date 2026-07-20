# Refactoring a Route to Use a Template — Worked Example

This is a worked example showing how to take a route that returns raw HTML as a string, and refactor it to use a Jinja2 template with `render_template()` instead. It uses a different scenario than the Fro-Yo assignment, so you can see the pattern without just copying the answer — apply the same steps to your own `froyo` and `froyo_results` routes.

## Before: Returning Raw HTML as a String

```python
@app.route('/sports')
def choose_sport():
    return """
    <form action="/sports_results" method="GET">
        What's your favorite sport? <br/>
        <input type="text" name="sport"><br/>
        What's your skill level? <br/>
        <input type="text" name="skill_level"><br/>
        <input type="submit" value="Submit!">
    </form>
    """

@app.route('/sports_results')
def show_sport_results():
    sport = request.args.get('sport')
    skill_level = request.args.get('skill_level')
    return f'You play {sport} at a {skill_level} level. Nice!'
```

This works, but the HTML is stuck inside a Python string — no syntax highlighting, no editor support, and it gets unreadable fast as a page grows.

## After: Refactoring to Use Templates

**Step 1: Create a template file for each route**, inside your project's `templates/` folder.

`templates/sports_form.html`:
```html
<form action="/sports_results" method="GET">
    What's your favorite sport? <br/>
    <input type="text" name="sport"><br/>
    What's your skill level? <br/>
    <input type="text" name="skill_level"><br/>
    <input type="submit" value="Submit!">
</form>
```

`templates/sports_results.html`:
```html
You play {{ sport }} at a {{ skill_level }} level. Nice!
```

**Step 2: Update your routes to build a `context` dictionary and call `render_template()` instead of returning a string directly.**

```python
from flask import Flask, render_template, request

@app.route('/sports')
def choose_sport():
    return render_template('sports_form.html')

@app.route('/sports_results')
def show_sport_results():
    context = {
        'sport': request.args.get('sport'),
        'skill_level': request.args.get('skill_level')
    }
    return render_template('sports_results.html', **context)
```

Notice:
- `render_template()` takes the template's filename first, then the `context` data unpacked with `**`.
- Inside the template file, each key from `context` gets referenced with double curly brackets: `{{ key }}`.
- The form page (`choose_sport`) doesn't need any dynamic data, so it can call `render_template()` with just a filename and no context.

## Applying This to Your Assignment

To refactor `froyo` and `froyo_results`:

1. Move the HTML from each route into its own file inside `templates/`.
2. Replace each f-string variable (like `{flavor}`) with the matching Jinja2 syntax (`{{ flavor }}`) in the template.
3. Build a `context` dictionary in `froyo_results` with the values you're pulling from `request.args`.
4. Replace each route's `return` statement with `render_template('yourfile.html', **context)`.

For more on how templates and `render_template()` work, see [Module 2, Lesson 1: Templating](../Lessons/module-2/lesson-1.md).
