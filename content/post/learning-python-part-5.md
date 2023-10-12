---
timeToRead: 5
authors: []
title: 'Learning Python: Part 5 - Functions'
excerpt: Exploring the fundamentals of functions in Python.
date: 2023-01-04T07:00:00+00:00
hero: "/images/download-12.jfif"
---

## Introduction

Welcome to the fifth part of my "Learning Python" series. In this section, we'll delve into the world of functions in Python. Functions are a powerful tool for making your code more reusable and organized. We'll explore how to define and use functions and showcase their role in structuring complex programs. Let's get started!

## Understanding Functions

In Python, functions are a way to encapsulate a block of code that performs a specific task. They enhance code reusability and maintainability by breaking down a program into smaller, manageable pieces. Three key components make up a function:

- **_`def` Statement_**: The `def` keyword tells Python that you're defining a new function.
- **_Function Name_**: You provide a name for the function, which helps identify and call it later.
- **_Function Script_**: This is where you write the code that the function will execute.

Let's create a simple function for a greeting as an example:

```python 
def greeting(name):
	print('Hello', name)

# Main program
Input_name = input('What is your name?'\n)

greeting(Input_name)
```

In this example, we define a function named greeting that takes a parameter called name. Inside the function, we use the print statement to display a greeting message with the provided name.

The main program section takes user input for their name, assigns it to the variable input_name, and then calls the greeting function with input_name as an argument.

Functions make your code modular and easy to read, but their real power shines when used to organize more complex programs.

## Organizing Code with Functions

Let's explore how functions can enhance code organization using a slightly more complicated program. In this example, we'll create a function to fetch weather information for a city using an external API.

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

In this program, we want to retrieve weather information for a specified city using an external API. To achieve this, we define two functions:

- **_weather_info()_**: This function handles the API request and data extraction. It prompts the user for the city name, constructs the API URL, sends the request, and parses the JSON response to extract relevant weather information. The data is then stored in a dictionary and returned to the main program.

- **_main()_**: The main program function calls weather_info() to obtain the weather data and then displays it to the user in a user-friendly format.

By breaking down the program into these two functions, we achieve better code organization, readability, and maintainability. Each function has a clear purpose, making the program easier to understand and modify.

## Conclusion

In this part of my Python learning journey, we've explored the world of functions. Functions are a fundamental building block in Python, enabling you to create reusable and organized code. Whether it's a simple greeting or a complex weather information retrieval system, functions play a crucial role in structuring your programs. As we continue this series, we'll delve deeper into Python's capabilities and explore more advanced topics and practical applications. Python's versatility makes it a powerful language for various tasks, and I'm excited to share more Python insights with you in the upcoming posts. Stay tuned!