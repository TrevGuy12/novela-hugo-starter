---
timeToRead: 3
authors: []
title: 'Learning Python: Part 1'
excerpt: Learning the fundamentals of python
date: 
hero: "/images/download-1.png"

---
# Python

Recently I have been learning the basics of the python programming language as it is an invaluable tool for my future career in computer science.

The course I have been following is named "Practical Python for Beginners" on Pluralsight. This site goes through Data types, input/output, conditionals, imports, lists, loops, and a few other python commands and features, I will be going through and explaining what I've learned in each section, hope you will follow along with me. 

## Data types

The first thing I learned with python is the different data types. 

There are four different data types in total. Floats, strings, booleans, and integers.

A Float is any numerical value with a decimal point:

```python
tax = 0.3
```

A string is a "string" of characters or words enclosed by quotations

    name = "Trevor"

A boolean is a true or false statement

    Its raining = false
    its sunny = true

An int or integer is a whole value

    amount = 10

## Inputs and Outputs

The second thing in this section was inputs and outputs. 

An input is a "task" you assign to a program and an output is the result of said task, for example:

    length = 10
    width = 5
    area = length*width
    print(area)

Another slightly more complicated example of this would be: 

    hello = "Hello"
    name = input("What's your name\n")
    greeting = hello + " " + name
    print(greeting)