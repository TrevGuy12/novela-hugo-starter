---
timeToRead: 5
authors: []
title: 'Learning Python: Part 4 - Dictionaries and JSON'
excerpt: Exploring the fundamentals of dictionaries and JSON in Python.
date: 2022-12-28T07:00:00+00:00
hero: "/images/download-11.jfif"
---

## Introduction

Welcome to the fourth part of my "Learning Python" series. In this section, we'll dive into the fundamental concepts of dictionaries and explore JSON (JavaScript Object Notation). Dictionaries are powerful data structures that allow you to store key-value pairs, while JSON is a widely used data format for communication between websites. Let's get started!

## Dictionaries

### Creating Dictionaries

Dictionaries in Python are similar to lists but with a twist—they can hold keys associated with values. You create a dictionary by assigning it to a variable and defining the key-value pairs within curly braces:

```python 
Dictionary = {'key1':'value1', 
        	  'key2':'value2', 
        	  'key3':'value3'}
```

Dictionaries can be used for a wide variety of tasks. For example, let's create a movie showtime script using a dictionary:

```python
current_movies = {'The Grinch':'11:00am', 'Rudolph':'1:00pm', 'Frosty The Snowman':'3:00pm', 'Christmas Vacation': '5:00pm'}

print("we are currently showing the following movies:")
 for key in current_movies:
     print(key)

movie = input('What movie would you like show times for?\n')

showtime = current_movies.get(movie)
	if showtime == None:
		print("we are not showing this movie at the current time")
else:
	print(movie, 'is playing at', showtime)
```

In this script, we create a dictionary named current_movies with movie names as keys and showtimes as values. We then print a list of currently showing movies by iterating through the dictionary's keys.

The user can input the name of a movie they want showtimes for. The script uses the get() method to retrieve the showtime associated with the user's input. If the movie is not found in the dictionary, it responds with **_"We are not showing this movie at the current time."_**

## JSON (JavaScript Object Notation)

JSON, short for JavaScript Object Notation, is a widely used data format for communication between websites. It primarily consists of nested lists and dictionaries. Here's an example:

```python
contacts = {
	"number":4,
    "students":
    [	
        {"name":"Sarah Holdernes", "email":"sarah@exsample.com"},
        {"name":"Bob Edge", "email":"bob@exsample.com"},
        {"name":"David Hering", "email":"david@exsample.com"},
        {"name":"Samantha Red", "email":"samantha@exsample.com"},
    ]

}
```

In this example, we define a dictionary named contacts. It has two key-value pairs: **_"number"_** and 4, which represents the number of students, and **_"students"_**, which has a list of dictionaries containing student names and email addresses.

JSON's flexibility and ease of use make it a valuable format for exchanging data between web services.

> When dealing with JSON it can get a bit confusing as there's a lot of dictionary/list inception.

## Conclusion

In this part of my Python learning journey, we've explored the essential concepts of dictionaries and JSON. Dictionaries allow us to manage key-value pairs efficiently, while JSON serves as a universal data format for web communication. As we continue this series, we'll delve deeper into Python's capabilities and explore more advanced topics and practical applications. Python's versatility makes it a powerful language for various tasks, and I'm excited to share more Python insights with you in the upcoming posts. Stay tuned!