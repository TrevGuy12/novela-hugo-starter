---
timeToRead: 3
authors: []
title: 'Learning Python: Part 4'
excerpt: 'Learning the fundamentals of python '
date: 2022-12-28T07:00:00+00:00
hero: "/images/download-11.jfif"

---
# Dictionaries and JSON

In this section, I will be explaining dictionaries and JSON. Dictionaries are just complex lists as they can hold keys and the keys can have values tied to them, and JSON (JavaScript Object Notation) is a format that websites use to communicate information with. Although JSON was originally created in JavaScript it's now a mostly universal format.

## Dictionaries

Creating a dictionary is slightly similar to creating a list as you set the dictionary to a variable and fill the rest in:

```python 
Dictionary = {'key1':'value1', 
        	  'key2':'value2', 
        	  'key3':'value3'}
```

Dictionaries can be used for a wide variety of tasks, for example, you can create a movie showtime script:

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

In this script, we are creating a dictionary under the variable `current_movies` and then inputting the current movies under the key and the show times under the value. Next, the script prints **_"we are currently showing the following movies:"_** and goes into the dictionary and pulls every movie name inside by calling the key _(That being what the names are associated with)_ and printing them all. 

Once the user knows what movies are playing we can ask what movie they want showtimes for, we do this by having the user input the name of the movie and storing that input under the `movie` a variable. 

Now that we know what movie the user wants showtimes for we can create a new variable for the showtime to rest in, inside this new variable we call the `currentmovies.get` function and grab the value that's assigned to the movie the user inputted and print the name of the movie they chose and its show time. 

If the user inputted a movie that isn't showing currently it will respond with **_"we are not showing this movie at the current time"._**

## JSON

JSON or JavaScript Object Notation is a very widely used format for web socket communication, it's mostly comprised of a series of lists and dictionaries:

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

The example above is the most basic form of JSON. This dictionary is set under the variable `contacts`, inside the dictionary the first **_"key"_** and **_"value"_** is `number` and `4` this represents the number of students in this class, next, there is a key by the name of `students` and the value is a list, inside that list, there is another dictionary with the names and emails of the students. 

> When dealing with JSON it can get a bit confusing as there's a lot of dictionary/list inception.