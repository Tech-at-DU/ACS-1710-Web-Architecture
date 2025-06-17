# Conditional Rendering with Templates

## WEB 1.1 - Module 2: Lesson 3

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Use Jinja2 if statements to conditionally render information in a template.

# Videos 🎥

<aside>
🚨 This video references material in the next lesson "Loops in Templates". It may be worth reading the material there before watching this video!

</aside>


<!-- [Vid 1 - Generating different views via conditional statements in the Jinja2 template syntax](https://file.notion.so/f/f/6004cc36-d69e-461f-a1c5-8e5078ac8f6b/e22199cd-31ad-4b5b-8268-51953e9a9037/9_Template_Conditionals.mov?table=block&id=37a0a656-14d2-4b01-9f33-c33188af3418&spaceId=6004cc36-d69e-461f-a1c5-8e5078ac8f6b&expirationTimestamp=1728064800000&signature=PDZBVpzjRt_BDoaJh2RpFrMfikdS8COyzUoN7UmbXZU&downloadName=9_Template_Conditionals.mov) -->

[Vid 1 - Generating different views via conditional statements in the Jinja2 template syntax](https://youtu.be/QnY-WcDyE4k)

<!-- # Exercises 💪

Complete the exercise in [this repl.it](https://repl.it/team/WebArchitecture/Module-202JinjaIfStatements) and submit your work. -->

# Written Companion 🗒

<aside>
🤔 What if we need to render different views based on the `context` values created by the user within the same route URL?

</aside>

---

The `Jinja2` templating syntax supports conditional statements and can render different views depending on the values within the `context` object passed to the template.

To utilize conditional statments in `Jinja2`, the if statement must be wrapped in a single curly bracket and percent sign as follows: `{% if/elif/else boolean expression %}`.

```python
# a Python route with one route variable and a context object
@app.route('/fact/<animal>')
def animal_fact(animal):

   context = {
       'animal': animal
   }

   return render_template('fact.html', **context)
```

```html
<! -- conditional statements in Jinja2 -- >
{% if animal == 'aardvark' %}
   Aardvarks can eat up to 50,000 insects each night! They swallow their food whole, without chewing it.
{% elif animal == 'penguin' %}
   A penguin’s black and white plumage serves as camouflage while swimming.
{% elif animal == 'zebra' %}
   A zebra's stripes serve to dazzle and confuse predators and biting insects.
{% else %}
   I don't have any facts about that animal. Please try again!
{% endif %}
```

Note: notice that the conditional loop always ends with an {% endif %} statement! A syntax error will occur if this does not get included.
