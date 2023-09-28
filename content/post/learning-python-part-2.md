---
timeToRead: 5
authors: []
title: 'Learning Python: Part 2 - Conditional Statements and Imports'
excerpt: Exploring conditional statements and package imports in Python.
date: 2022-12-13T07:00:00+00:00
hero: "/images/download-5.jfif"
---

### Introduction

Welcome to the second part of my "Learning Python" series. In this section, we'll delve into Python's different conditional statements and the art of importing external Python packages. Conditional statements enable us to create complex programs that respond to specific inputs, while package imports open up a world of possibilities by leveraging the work of the vast Python community. Let's dive in!

### Conditional Statements

Conditional statements are the building blocks of logic in Python, and they empower us to create programs that make decisions based on specific conditions. There are three primary conditional statements in Python: `if`, `elif`, and `else`.

### The `if` Statement

The `if` statement allows us to execute a block of code if a particular condition is met. Here's a simple example:


```python
color = input("is red your favorite color? y/n\n")
if color = y:
	print("Nice")
else:
	Print("wrong")
```

The elif Statement
The elif statement is a combination of if and else that lets us handle more complex conditions. For instance:

```python
temp = 75

if temp > 85:
	print("Its to hot, stay inside!")
elif temp < 60:
	print("Its to cold, stay inside!")
else:
	print("Enjoy the weather!")
```

## Imports

Python's strength lies in its vast ecosystem of packages and libraries, created by a thriving community of programmers. These packages extend Python's capabilities, allowing us to perform a wide range of tasks without writing hundreds of lines of code.

### Installing Packages

To begin using packages, we first need to install them using the pip function. For example, to install the random package:

```python
pip install random
```

pip is Python's package installer, and it's how you add new packages to your Python environment.

### Importing Packages

Once installed, you can import packages into your Python files. For instance, to use the random package:

```python
import random 
```

With the package imported, you can access its functions and variables in your code. Here's an example using the random package to create a simple rock, paper, scissors game:

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

In this example, we import the random package to make a random choice for the NPC's move in the game. The game logic is driven by conditional statements.

### Conclusion

In this installment of my Python learning journey, we've explored conditional statements and the power of importing external Python packages. These fundamental concepts pave the way for creating more complex and feature-rich Python programs. As we continue this series, we'll venture into more advanced Python topics and practical applications. Python's versatility and the vast Python community make it an exciting language to learn, and I hope you're as eager as I am to explore its endless possibilities. Stay tuned for more Python adventures!