# Leveraging the `Datetime` Library

## ACS 1710 - Module 4: Lesson 3

# Learning Outcomes 💫

By the end of this lesson, you should be able to...

- Use the `strftime()` library function to format datetime objects using a custom format.
- Use the `strptime()` library function to parse strings containing dates and times and turn them into datetime objects.

# Videos 🎥

<!-- [Vid 1 - using `datetime` objects](https://file.notion.so/f/f/6004cc36-d69e-461f-a1c5-8e5078ac8f6b/1c38acb9-9167-41eb-a4a1-960e75f55a15/16_Datetimes.mov?table=block&id=f1da28a3-510e-4b77-a14e-eea87bacd1c9&spaceId=6004cc36-d69e-461f-a1c5-8e5078ac8f6b&expirationTimestamp=1728064800000&signature=81dkYL2UXJ13Jb1gMhKZZn9XEkyxFVTghki4ZXq-arE&downloadName=16_Datetimes.mov) -->

[Vid 1 - using `datetime` objects](https://youtu.be/febQEicMPfU)

Vid 1 - using `datetime` objects

# Exercises 💪

Test your understanding of the `datetime` library with the questions below. Try to answer each one yourself before checking the answer key.

1. How do you create a `datetime` object representing the current date and time?
2. Which method converts a `datetime` object into a formatted string? Which method does the reverse, converting a string into a `datetime` object?
3. What format code represents a 4-digit year? What about a 2-digit day?
4. Write the format string you'd pass to `strftime()` to get a date in the form `09/02/2020` (month/day/year).

<details>
<summary>Answer Key</summary>

1. `datetime.now()`, e.g. `datetime_obj = datetime.now()`.
2. `strftime()` converts a `datetime` object to a string; `strptime()` converts a string to a `datetime` object.
3. `%Y` for a 4-digit year; `%d` for a 2-digit day.
4. `'%m/%d/%Y'`

</details>

# Written Companion 🗒

<aside>
🤔 How can we easily create objects that represent specific times and dates in a universally accepted format?

</aside>

---

Python has a built-in library called `datetime`. This library provides developers access to the `datetime` object—an object containing date and time in a common format.

A `datetime` object can easily be created using the `datetime.now()` method and assigning it to a variable.

```python
# creating a new datetime object in python
from datetime import datetime

datetime_obj = datetime.now()

print(datetime_obj)
# 2020-09-02 21:17:19.511047
```

The `datetime` object has many properties but the some of the most commonly used ones include:

- datetime_obj.day
- datetime_obj.month
- datetime_obj.year
- datetime_obj.hour
- datetime_obj.minute

### Converting `datetime` objects

A `datetime` object can be converted to a string using the `strftime()` method.

When converting `datetime` objects in this fashion—format codes can be employed to more easily grab specific portions of the date or time. Some common format codes include:

- %Y = the year
- %m = the month
- %d = the day
- %H = the hour
- %M = the minute

A complete list of format codes can be found here: https://docs.python.org/3/library/datetime.html

```python
# utilizing the `strftime()` method with format codes
print(datetime_obj.strftime('%Y-%m-%d'))
# '2020-09-02'
```

*Fig 1 - printing only the year, month, and day as a single string*

A string can be converted to a `datetime` object using the `strptime` method:

```python
# creating a new `datetime` object via the `strptime()` method
another_date = datetime.strptime('2020-09-03', '%Y-%m-%d')
print(another_date) # 2020-09-03 00:00:00
```

*Fig 2 - creating a new `datetime` object via a string and format codes to specify which numbers represent what `datetime` value*
