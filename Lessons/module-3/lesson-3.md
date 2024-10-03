# Working with JSON Objects

## ACS 1710 - Module 3: Lesson 3

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Write JSON objects (i.e. Python dictionaries) containing nested data.
- Retrieve values from nested JSON objects using Python dictionary syntax.

# Video Companions 🎥

[Vid 1 - Creating `JSON` objects in Python](https://file.notion.so/f/f/6004cc36-d69e-461f-a1c5-8e5078ac8f6b/3dc7b9d7-e726-446e-af99-d96b51921a0f/11_JSON.mov?table=block&id=2217a171-86fc-4225-8817-8aed6ab69b50&spaceId=6004cc36-d69e-461f-a1c5-8e5078ac8f6b&expirationTimestamp=1728064800000&signature=HFVYwWo3eUUZDUZaC6YEDJUfXxN0WGLJ6P1SIqIVqrw&downloadName=11_JSON.mov)

https://youtu.be/t1t6crpMRgo

[Vid 2 - Returning `JSON` objects in a Flask route](https://file.notion.so/f/f/6004cc36-d69e-461f-a1c5-8e5078ac8f6b/491014e3-67e4-48f6-a672-ceabdefb296a/12_JSON_Route.mov?table=block&id=baf6fc02-2472-4e1f-a975-c7fd2c8c11be&spaceId=6004cc36-d69e-461f-a1c5-8e5078ac8f6b&expirationTimestamp=1728064800000&signature=-G616wNhVlg_v02bD3_CQ6F3CWbxWLhW2B8IU2vlLWQ&downloadName=12_JSON_Route.mov)

https://youtu.be/HztSwyxdQzo

<!-- # Exercises 💪

Complete the exercise in [this repl.it](https://repl.it/team/WebArchitecture/Module-302DictionariesPractice) and submit your work. -->

# Written Companion 🗒

<aside>
🤔 How do we efficently package information so that tens of thousands of users can be served as quickly as possible?

</aside>

---

`JSON` stands for **JavaScript Object Notation**. 

<aside>
🚨 A `JSON` object can be used by languages other than Javascript! `JSON` objects find their origins in Javascript and therefore look similar to them—but `JSON` objects also look quite similar to Python objects too.

</aside>

<aside>
💡 Many programming languages can interpret `JSON` objects because they are nothing more then an **object notation**—which means that the object always uses the same predictable **key-value** pairs.

</aside>

```json
{
	"type": "success",
	"value": {
		"id": 493,
		"joke": "Chuck Norris can binary search unsorted data.",
		"categories": ["nerdy"]
	}
}
```

Fig *1 - a `JSON` object with several **key-value** pairs.*

- *Note: A `JSON` object looks identical to Python's `dictionary` data structure because both use the same **key-value** pair format*

<aside>
🚨 Notice that the `JSON` object in *Fig 1* does not have any variable declarations! `JSON` objects exist to be packaged and/or sent across the internet. As a result, a `JSON` file only contains object data **to be assigned by the requesting function.**

</aside>

Since `JSON` objects always use the same notation pattern and can be transported efficently, they have become a standard API format to utilize for passing data across networks.

```python
# a JSON object translated into Python
my_info = {
   'name': 'Fluffy',
   'likes': ['tennis balls', 'walks'],
   'address': {
       'street': '555 Post St',
       'city': 'San Francisco'
   }
}

# accessing the `my_info` object's `address` property, then the `street` property
street_address = my_info['address']['street']
```

*Fig 2 - a `JSON` object implemented into a Python file*

- *Consider how a `JSON` object can be assigned to a Python variable—would it be possible to import the `my_info` data from a `JSON` object instead of hard coding it here?*
- *Note: Notice how each of the object's properties must be accessed to go deeper into the child objects*
