---
timeToRead: 2
authors: []
title: 'Learning Python: Part 3'
excerpt: Learning the fundamentals of python
date: 2022-12-15T07:00:00+00:00
hero: "/images/download-4.jfif"

---
# Lists and Loop

In this section, I will be talking about lists and loops. A list is a collection of numbers and or strings, the list function in python is shown by square brackets, `[]`. Loops, as the name suggests, are scripts that will loop for a pre-determined amount.

## Lists

Creating a list is fairly easy, all you need to do is create a variable to set the list under and then create the list using square brackets:

```python
list = [1, 2, 3, 4]
```

Lists can be very useful if you need to store many different strings or values but you don't want to clutter your code by creating a different variable for each thing. for example, if you have 5 different songs that one could choose to listen to you wouldn't want to make a variable for each song instead you could do the following:

```python 
songs = [song_1, song_2, song_3, song_4, song_5]
```

## Loops

Let's say you wanted to make an itemized list of expenses for the day, but you want to be able to enter the purchases as the day goes on, you could make use of a loop to enter them as you go

Doing this requires you to create an empty list and have the loop add to it:

```python
total = 0
expenses = []

for i in range (7):
	expenses.append(float(input("enter expense")))
total = sum(expenses)
print("You spent $", total)
```

What the script above is doing is creating a total value equal to 0 so we have a variable to do the addition for the expenses, then we create a list with the name expenses so we can add values to it later.

Next is where the loop comes in, we are creating a loop that will repeat itself 7 times, each time the loop kicks off it's taking your input and adds it to the expenses list via the append command.

Then it takes all the values in expenses and adds them together and puts them under the total variable. Once that is completed it prints "You spent $X" and adds the total amount spent.