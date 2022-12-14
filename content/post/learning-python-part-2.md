---
timeToRead: 2
authors: []
title: 'Learning Python: Part 2'
excerpt: Learning the fundamentals of python
date: 2022-12-13T07:00:00+00:00
hero: "/images/download-5.jfif"

---
# Python

This is the second part of my learning python series, in this section I will be telling you some of Python's different conditional statements and importing external python packages. Conditional statements can be used to create complicated programs to complete a wide variety of tasks that involve logic. Also, python has a huge community of programmers who have created packages you can import and leverage so you wouldn't need to write hundreds of lines of code for a simple project.

### Conditional Statements

A conditional statement is a statement that reacts based on a specific input, there are three that I have learned, `if, elif, else` an example of if and else would be:

```python
color = input("is red your favorite color? y/n\n")
if color = y:
	print("Nice")
else:
	Print("wrong")
```

elif is a mix of if and else, it can be used to make a more complex conditional statement, an example of this would be:

```python
temp = 75

if temp > 85:
	print("Its to hot, stay inside!")
elif temp < 60:
	print("Its to cold, stay inside!")
else:
	print("Enjoy the weather!")
```

### Imports

Being able to import packages opens the door to so much more as you have a community of people who have created scripts that allow you to do so many different things, a few examples of different packages are, random, requests, and so many more.

Packages can be installed by using the pip function:

```python
pip install random
```

The pip function is how you can install any packages in python.

Once you have all the packages you want to be installed you need to import them into your python files, so if you wanted to use the random package you would have to do the following:

```python
import random 
```

From here you can start to write your code and once you use the variables that are contained within the random package they will be pulled as you have imported them into your project.

```python
import random

NPC_Choice = random.choice (['rock', 'paper', 'scissors'])

Player_Choice = input("Do you want - rock, paper, or scissors?\n")

if NPC_Choice == Player_Choice:
	print("tie :|")
elif Player_Choice == "rock" and NPC_Choice == "scissor":
    print("You win :)")
elif Player_Choice == "paper" and NPC_Choice == "rock":
    print("You win :)")
elif Player_Choice == "scissor" and NPC_Choice == "paper":
    print("You win :)")
else:
    print("You lose :(")
```

The example above is a rock, paper, scissors game that involves conditional statements and an imported package that allows it to function. 