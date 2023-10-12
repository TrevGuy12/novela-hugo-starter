---
timeToRead: 5
authors: []
title: 'Learning Python: Part 3 - Lists and Loops'
excerpt: Exploring the fundamentals of lists and loops in Python.
date: 2022-12-15T07:00:00+00:00
hero: "/images/download-4.jfif"
---

## Introduction

Welcome to the third part of my "Learning Python" series. In this section, we'll dive into the fundamental concepts of lists and loops in Python. Lists allow you to store collections of numbers and strings, while loops are essential for executing scripts repeatedly for a predetermined number of times. Let's get started!

## Lists

### Creating Lists

Creating a list in Python is straightforward. You need to define a variable and use square brackets, `[]`, to enclose the list elements:

```python
list = [1, 2, 3, 4]
```

Lists are incredibly useful when you want to store multiple values without cluttering your code with separate variables. For instance, if you have five different songs that one could choose to listen to, you can create a list like this:

```python 
songs = [song_1, song_2, song_3, song_4, song_5]
```

## Loops

### Introduction to Loops

Loops, as the name suggests, allow you to execute a block of code repeatedly for a predefined number of iterations. Let's explore how loops work with a practical example.

### Iterating with a Loop
Imagine you want to create an itemized list of expenses for the day, but you want to add expenses as the day goes on. You can achieve this using a loop to input expenses as you make them.

Here's how you can do it in Python:

```python
total = 0
expenses = []

for i in range (7):
	expenses.append(float(input("enter expense")))
total = sum(expenses)
print("You spent $", total)
```

In this script, we start by initializing a total variable to 0 to keep track of the total expenses. We also create an empty list called expenses where we'll store the individual expenses.

Next, we use a for loop to repeat a block of code seven times. Inside the loop, we use the append() method to add the expenses entered by the user to the expenses list.

After the loop completes, we calculate the total expenses using the sum() function and store the result in the total variable. Finally, we print the total amount spent.

## Conclusion

In this part of my Python learning journey, we've explored the essential concepts of lists and loops. Lists provide a convenient way to store collections of data, while loops enable you to perform repetitive tasks efficiently. As we continue this series, we'll dive deeper into Python's capabilities and explore more advanced topics and practical applications. Python's versatility makes it a powerful language for various tasks, and I'm excited to share more Python insights with you in the upcoming posts. Stay tuned!