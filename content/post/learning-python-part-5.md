---
timeToRead: 3
authors: []
title: 'Learning Python: Part 5'
excerpt: 'Learning the fundamentals of python '
date: 2023-01-04T07:00:00+00:00
hero: "/images/download-12.jfif"

---
# Functions

In python, functions are a way to make your code more recyclable and more organized, there are three main components for functions.

There is the `def` function that tells python that you want to create a new function, next you attribute a name to the function, and once it's named you write the script in the function.

for example, I will write a simple function for a greeting:

```python 
def greeting(name):
	print('Hello', name)

# Main program
Input_name = input('What is your name?'\n)

greeting(Input_name)
```

What I did above was created a function named `greeting` with a variable called `name` this helps the function know where to put the input inside of the print statement.

Once the function is created then we move into the main program, where it asks for the user's name and attaches it to the variable `Input_name`, once this is done we can call the `greeting` function and put the `Input_name` variable inside.

Because this is just a simple print statement inside of the function it doesn't show just how useful this is for organizing code so I will show you a slightly more complicated program where functions can be used for organization:

```python
import requests

def weather_info():
    api_key = "b22d809152a6b40b7be2ad3f4a01fc2b"
    city = input("What city do you want to know the weather for?\n")
    url = "https://api.openweathermap.org/data/2.5/weather?q=" + city + "&appid=" + api_key + "&units=imperial"

    request = requests.get(url)
    json = request.json()

    description = json.get("weather")[0].get("description")

    temp_min = json.get("main").get("temp_min")
    temp_max = json.get("main").get("temp_max")

    return {'description': description,
            'temp_min': temp_min,
            'temp_max': temp_max}

def main():
    weather_dict = weather_info()
    print("Today the weather looks like", weather_dict.get('description'))
    print("The min temp is", weather_dict.get('temp_min'), "Degrees. The max temp is", weather_dict.get('temp_max'), "Degrees.")
main()
```

To summarise what happens with the program above there is a weather website that allows users to access their API, in order for the script to access the API it needs a key which the website kindly provides for you.

Now you just need to copy that key into a variable and plug that variable in the URL, this allows the script to enter the website's API. with access to the website we can now find out the current data for a cities weather, and return it with a few print statements.

How do functions play a role in this program?

Well it allows us to break it down into more manageable sections, for example, the `weather_info` function goes into the API and grabs the weather data for the chosen city then returns it to the program where we pick through the now gathered city weather data and find three different pieces of data we want, the `description`, and the `temp_min` / `temp_max`.

After we have collected the pieces of data we actually want we store them in a dict/dictionary, which our main program function can use to tell the end user the weather in the city.