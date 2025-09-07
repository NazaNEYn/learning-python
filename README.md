
# Table of Contents
---
- [Printing outputs](#printing-outputs)
  - [String Concatenation](#string-concatenation-combining-strings)
- [Input Function](#input-function)
- [Variables](#variables)
- [Dat Types](#dat-types)
- [Subscripting](#subscripting)
- [Integer (Whole Number)](#integer-whole-number)
  - [Large Integer](#large-integer)
- [Float = Floating point number](#float--floating-point-number)
- [Boolean](#boolean)
- [Type Conversion Functions (Type casting)](#type-conversion-functions-type-casting)
- [Modulo Operator (%)](#modulo-operator-)
- [Condituinal Statement (if / else)](#condituinal-statement-if--else)
- [Nested if / else](#nested-if--else)
- [if / elif/ else](#if--elif-else)
- [Multiple if](#multiple-if)
- [Logocal Operators](#logocal-operators)
- [Random Module](#random-module)
- [Lists](#lists)
- [Tuple](#tuple-)
- [Constant](#constant-)
- [For Loop](#for-loop)
- [Function](#function)
- [While Loop](#while-loop)
- [Dictionary](#dictionary)
  - [Assigning a new key](#assigning-a-new-key)
  - [Reassigning a new key](#reassigning-a-new-key)
  - [Wiping/deleting the dictionary](#wipingdeleting-the-dictionary)
  - [Nesting lists inside a dictionary](#nesting-lists-inside-a-dictionary)
- [How to loop through a dictionary](#how-to-loop-through-a-dictionary)
- [Ways to import modules](#ways-to-import-modules)
- [Aliasing Modules](#aliasing-modules)
- [Slicing](#slicing)
- [return keyword](#return-keyword)
- [Q: So one of the use case for function is to make some variable local and make them stop being global?](#q-so-one-of-the-use-case-for-function-is-to-make-some-variable-local-and-make-them-stop-being-global)
- [Debugging](#debugging)
- [Logging](#logging)
- [OOP (Object-Oriented Programming)](#oop-object-oriented-programming-)
- [Creating classes](#creating-classes)
- [self.](#self-)
- [Class inheritance](#class-inheritance)
- [What Goes in the Main File?](#what-goes-in-the-main-file)


--------------------------------
## Printing outputs : <br>
```python
print("Hello World!")
```
<br>
Instead of writing multiple lines like

```python
print("Hello World!")
print("Hello World!")
print("Hello World!")
```

We could write 
```python
print("Hello World! \nHello World! \nHello World")

# Hello World 
# Hello World 
# Hello World
```

### String Concatenation (Combining Strings)

```python
# Hello Naz

# We could add an empty strng in between the words :
print("Hello" + " " + "Naz")

# or
print("Hello " + "Naz")
# Hello Naz

# or
print("Hello" + " Naz")
# Hello Naz
```

----------------------------------------------
## Input Function

```python
input("A prompt for the user")
```
Example:

```python
input("What is your name?")
```


```python
print("Hello " + input("What is your name?") + "!")
```

----------------------------------------------

## Variables 
Variable is somtheing that can be changed or varied.

```python
name = input("What is your name?")
print(name)
```

----------------------------------------------


## Dat Types

1. String
2. Integer
3. Float
4. Boolean

----------------------------------------------


## Subscripting

Pulling out a particular element from a string and the number between square brackets determines which character you're going to pull out

```python
print("Hello"[0])

# H
```

* Tip :
We can use `-` and get the last character

```python
print("Hello"[-1])

# o
```

----------------------------------------------

## Integer (Whole Number)

```python
print(123 + 456)

# 468
```

## Large Integer 

For writing big numbers like 123,456,786 we use `_` instead of `,`
```python
print(123_456_789)

# 123456789
```
----------------------------------------------

## Float = Floating point number

```python
print(3.14159)

# 3.14159
```

----------------------------------------------
## Boolean

```python
print(True)
print(False)
```

----------------------------------------------

## Type Conversion Functions (Type casting)


**`int()`** Converts a value to an integer. If the input is a float, it truncates the decimal part (rounds towards zero). If the input is a string, it must represent a whole number.

```python
print(int(55.222))
#55

print(int(55.9222))
#55
```

**`float()`** Converts a value to a floating-point number. If the input is an integer, it adds a decimal part (e.g., 5 becomes 5.0). If the input is a string, it must represent a valid number (integer or decimal).

```python
print(float(55.222))
# 55.222

print(float(55.9222))
# 55.9222
```

**`round()`** is used to round a number to the nearest integer or to a specified number of decimal places.

```python
print(round(55.222))
#55

print(round(55.9222))
#56
```

It lets you add a second argument to specify how many decimal places to show for rounding is:

`round(number, ndigits)`

```python
print(round(55.2255452 , 2))
# 55.23

print(round(55.9222 , 1))
# 56.9
```
----------------------------------------------
## Modulo Operator (`%`)

Simple Example: Cookies and Bags

Let's say you have `10` cookies and each bag holds `3` cookies.

You fill the first bag: You use `3` cookies. You have `7` left.

You fill the second bag: You use another `3` cookies. You have `4` left.

You fill the third bag: You use another `3` cookies. You have `1` left.

Can you fill another bag? No, because you only have `1` cookie left, and a bag needs `3`.

So, the number of cookies **left over** is 1.

In Python, this would be:
`10 % 3` which equals 1.



```python
print(10 % 3)  # Output: 1 (10 divided by 3 is 3 with a remainder of 1)
# 3 * 3 = 9 and 10 - 9 = 1

print(15 % 4)  # Output: 3 (15 divided by 4 is 3 with a remainder of 3)
# 4 * 3 = 12 and 15 - 12 = 3

print(7 % 2)   # Output: 1 (7 divided by 2 is 3 with a remainder of 1 - useful for checking odd/even)
# 2 * 3 = 6 and 7 - 6 = 1

print(20 % 5)  # Output: 0 (20 divided by 5 is 4 with a remainder of 0)
# 5 * 4 = 0 and there is no remaining

print(5 % 20)  # Output: 5 (5 divided by 20 is 0 with a remainder of 5)
```

----------------------------------------------
## Condituinal Statement (`if / else`)


```python
if condition:
    do this
else:
    do this
```

```python
height = int(input("How tall are you?\n"))

if height >= 120:
  print("You can enter to ride the rollecoaster")
else:
  print("sorry, you are short")
```

**Tip**
`=` is for assignment
`==` is for checking equality

----------------------------------------------
## Nested `if / else`



```python
if condition:
  if another condition:
    do this
  else:
    do this
else:
  do this
```

```python
height = int(input("How tall are you?"))

if height >= 120:
    print("You can ride")
    age = int(input("How old are you?"))
    if age >= 18:
      print("you have to pay 12$")
    else:
      print("you have to pay 7$")
else:
    print("Sorry you are short")
```

----------------------------------------------

##  `if / elif/ else`



```python
if condition1:
  do A
elif conditio2:
  do B
else:
  do This
```



```python
height = int(input("How tall are you?"))

# Prompt the user for their height and convert the input string to an integer.
# This variable will be used to determine initial ride eligibility.
height = int(input("How tall are you?\n")) # Added \n for better prompt display

# Check if the person meets the minimum height requirement for the ride.
if height >= 120:
    # If tall enough, inform the user they can ride and proceed to age-based pricing.
    print("You can ride")

    # Prompt the user for their age and convert the input string to an integer.
    # This variable will determine the specific ticket price.
    age = int(input("How old are you?\n")) # Added \n for better prompt display

    # Determine the ticket price based on age, using a clear tiered system.

    # If age is 12 or younger, apply the child price.
    if age <= 12:
        print("You have to pay 5$")
    # If age is 18 or older, apply the adult price.
    # This 'elif' ensures that ages 13-17 are correctly skipped for this condition.
    elif age >= 18:
        print("You have to pay 12$")
    # If none of the above conditions are met (i.e., age is between 13 and 17, inclusive),
    # apply the 'teen' or 'standard' price.
    else: # This implicitly covers ages > 12 and < 18 (i.e., 13, 14, 15, 16, 17)
        print("You have to pay 7$")

# If the person does not meet the minimum height requirement,
# inform them they cannot ride.
else:
    print("Sorry you are too short") 
```

----------------------------------------------
##  Multiple if


```python
if condition1:
  do A
if condition2:
  do B
if condition3:
  do C
```

It doesn't necessary need a `else` block.
----------------------------------------------

##  Logocal Operators


```python
A and B
# of both condictions are true = True
#if just one of them is true = False

C ord D
# if only either of them is true = True
# False or False = False

not E
```

----------------------------------------------

##  Random Module

What is `module? <br>
A module in Python is a very specific, low-level concept: it's literally a single .py file that contains Python code (functions, classes, variables). It's the most basic unit of code organization and reuse in Python.


The first thing that we need to do is to add `import random`. <br>
*[link](https://docs.python.org/3/library/random.html)*


```python
random_number = random.randint(1, 99)
# random numbes between 1-99
```


```python
random_number_0_to_1 = random.random()
print(random_number_0_to_1)
# Generates a random number between 0-1
```
----------------------------------------------


##  Lists

```python
variable = [item1, item2, item3]
```

```python
fruits = ["apple", "orange", "strawberry", "cherry"]
print(fruits[0])
# apple

print(fruits[-1])
# Gets the last one
# cherry
```

How to change a variable?

```python
fruits = ["apple", "orange", "strawberry", "cherry"]

fruits[1] = "banana"

print(fruits)
# ['apple', 'banana', 'strawberry', 'cherry']
```

How to add a new variable? (`append() function`)

```python
fruits = ["apple", "orange", "strawberry", "cherry"]

fruits.append("banana")

print(fruits)
# ['apple', 'orange', 'strawberry', 'cherry', 'banana']
```

How to add a list? (`extend() function`)
```python
fruits = ["apple", "orange", "strawberry", "cherry"]

fruits.extend(["banana", "melon", "lemon"])

print(fruits)
# ['apple', 'orange', 'strawberry', 'cherry', 'banana', 'melon', 'lemon']
```

----------------------------------------------
## Tuple :

Tuple is similar to a list<br>

Tuple:
`(1, 2, 3)`
Lits:
`[1, 2, 3]`

The difference between a `tuple` and a `list` is that you can't change the value in a `tuple` like you can in a `list`.<br>
You can't change the values in any way in a `tuple`. It is `immutable`.


**Convertin a tuple into a list**:

```python
my_tuple = (1, 2, 3)
list(my_tuple)
#[1, 2, 3]
```

----------------------------------------------


## constant :

In Python, the naming convention of using all capital letters (e.g., `STARTING_POSITION`, `PI`, `MAX_SPEED`) is a way for programmers to signal that a variable should be treated as a constant. However, unlike in some other programming languages, Python does not enforce this. You can technically change the value of STARTING_POSITION later in your code.<br>

The main purpose of this naming convention is to improve code readability and inform other programmers that they should not modify the value. It's a way of saying, "Hey, this value is meant to stay the same throughout the program's execution, so please don't change it!"

----------------------------------------------


## For Loop


```python
for item in list_of_items:
# Do spmething to each item
```
Example:

```python
fruits = ["apple", "strawberry", "melon"]
for fruit in fruits:
    print(fruit)

# apple     
# strawberry
# melon 
```

----------------------------------------------

## Function


```python
def name(args):
    pass
```

Example :

```python
def my_function():
    print("Hello")
    print("Bye")


my_function()

# Hello
# Bye
```
----------------------------------------------
## While Loop


```python
while something_is_true:
    # Do something 
    # The loop will stop hen something becomes false
```
----------------------------------------------
 ## Dictionary


```python
dictionary = {
    "key": "value",
}
```

Example:

```python
bio = {
    "name": "naz",
    "age": 31,
}

# {'name': 'naz', 'age': 31}
```

## Assigning a new key

```python
bio["is_employed"] = True
# {'name': 'naz', 'age': 31, 'is_employed': True}
```

## Reassigning a new key

```python
bio = {
    "name": "naz",
    "age": 31,
}

bio["name"] = "Ash"

# {'name': 'Ash', 'age': 31}
```

## Wiping/deleting the dictionary 

```python
bio = {
    "name": "naz",
    "age": 31,
}

bio = {}

# {}

# {'name': 'Ash', 'age': 31}
```


 ## Nesting lists inside a dictionary


```python
bio = {
    "name": ["Ash", "Max", "Naz"],
    "age": 31,
}

bio = {
    "name": ["Ash", "Max", "Naz", ["Alex", "John"]],
    "age": 31,
} 
```

### How to print out the values inside the nested lists?


```python
bio = {
    "name": ["Ash", "Max", "Naz"],
    "age": 31,
}

print(bio["name"][1])
# Max
```

```python
bio = {
    "name": ["Ash", "Max", "Naz", ["Alex", "John"]],
    "age": 31,
}

print(bio["name"][3][1])
# John 
```


 ## A nested dictionary


```python
user_profile = {
    "name": "Alex",
    "contact": {
        "email": "alex@example.com",
        "phone": "123-456-7890",
    },
    "status": "Active",
}


print(user_profile["contact"]["phone"])
# 123-456-7890
```
----------------------------------------------

 ## How to loop through a dictionary

When we loop through a dictionary, it loops through the `keys.

In this example each fruit is a `key` and the color is the `value`.
```python
color_box = {
    "apple": "red",
    "orange": "orange",
    "peach": "pink",
    "banana": "yellow",
}


# looping throgh `keys`
for fruit in color_box:
    print(fruit)

# looping through `values`
for fruit in color_box:
    print(color_box[fruit])

```



I wrote an *article* wite more details about looping through a dictionary.<br>
You can check it out **[HERE](https://nazanin-ashrafi.hashnode.dev/looping-through-dictionaries-in-python)**

----------------------------------------------
## Ways to import modules:

1. **`import`** <br>
 First we have to import the module by using the `import` keyword and the module name. <br>

For example:
`import random`
or
`import turtle`

### Now how to use it:

Example:
```
turtle = turtle.Turtle()
```

```python
turtle.Turtle()
# turtle is the module name
#and
# Turtle() is the name of the class
```

2. **`from...import..`**<br>


```python
from turtle import Turtle
# from is the keyword
# turtle is the module name
# import is the keyword
# Turtle the class name

turtle = Turtle()
```

3. **Importing everything:**<br>

`from turtle import *`

The asterisk (`*`) will let you import everything from the module.<br>

*NOTE:* It's not a good practice to use this type of importing.

----------------------------------------------
## Aliasing Modules:

Example:

```python
import turtle as t
```

`turtle = t.Turtle()`

*NOTE:* This is useful for when the module name is really long.

----------------------------------------------


## Slicing:

**The Simple Slice** `[start:end]` <br>
The most basic slice uses two numbers: a **start** and an **end**.

* **start:** This is the index where your slice begins. The item at this index is **included**.
* **end:** This is the index where your slice stops. The item at this index is **not included**.

For example, let's say we have a list of fruits: `fruits = ["apple", "banana", "cherry", "date", "elderberry"]`

`fruits[1:4]` would give you `["banana", "cherry", "date"]`. It starts at index 1 ("banana") and goes up to, but not including, index 4 ("elderberry").


**The Full Slice** `[start:end:step]` <br>

You can add a third number, the **step**, to control how you "walk" through the sequence.

* **step:** This tells Python how many items to skip after each one it grabs. The default is 1. If you set the step to 2, you'll get every second item.

`numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]`
`numbers[1:8:2]` would give you `[1, 3, 5, 7]`. It starts at index 1, goes up to but not including index 8, and grabs every second number.


| Syntax | Colons Used | What It Does |
| :--- | :--- | :--- |
| `my_list[1:8]` | Single colon `:` | Slices from index 1 to 8 (not including 8) with the default step of 1. |
| `my_list[1:8:2]` | Two colons `::` (a "double colon" operation) | Slices from index 1 to 8, taking every second item. |
| `my_list[::2]` | Two colons `::` | Shortcut for `my_list[0:len(my_list):2]`. Takes every second item from the beginning to the end. |


*Note:* <br>
The double colon `::` is not a different part of the syntax; it's just Python's way of saying **"leave the start and end values empty"** so you can jump right to the step.

| Form Field | Your Request (`my_list[1:8:2]`) | Shortcut (`my_list[::2]`) |
| :--- | :--- | :--- |
| **Start Index** | 1 | (leave blank) |
| **End Index** | 8 | (leave blank) |
| **Step** | 2 | 2 |

When you leave those fields blank, Python uses its default values: **start** becomes 0 and **end** becomes the end of the sequence. <br>
So, the double colon `::` is just a concise way to signal that you want to use the default start and end, but still specify a **step**.


----------------------------------------------


## `return` keyword :
In Python, if a function doesn't have a `return` statement, or if the return statement is reached without an explicit value (like just `return`), the function implicitly returns `None`. <br>

Coding partner
Imagine you send your robot helper 🤖 to go do a job.

If you tell the robot to "Go clean your room!" and it just does it, but you don't tell it to report anything back to you, the robot will just finish the job and then stand there quietly. That's like the function implicitly returning `None`. It did its job, but didn't give you a message or a toy back.

Now, if you tell the robot, "Go get me a snack!" and it comes back holding a cookie 🍪, that's like the function explicitly returning a **value** (the cookie).

So, if your function doesn't specifically give you something back with a `return` command, Python just assumes it gave you nothing important, which it calls `None`.
<br>

* The return statement's job in a function is precisely like **reporting back** and **bringing you a value**.<br>

Think of it this way:

When you call a function, you're asking it to perform a task.

Once it's done with that task, the return statement is how the function gives you the result of its work, or simply a confirmation that it finished.

Without return, the function might do its job internally (like printing something), but it doesn't hand anything back to the part of the code that called it. If it doesn't explicitly hand anything back, Python automatically hands back None, which means "nothing special."
<br>

That's the primary purpose of return in a function: it **fetches the value** computed or determined within the function so you can **use that value in the code that called the function**.

It's like a messenger delivering a specific piece of information from the function's internal work back to the main operation.

<br><br>

### when we dont use return in a function, we cant just call the function and expect to get an output but when we use return and if we call the fucntion, we'll get an output, right?

Here's a slightly more precise way to put it:

* **When a function does NOT use `return` (or `return` is used without an argument):**

   *  You can call the function to make it perform actions (like changing variables, printing things to the console, writing to files, etc.).

  * However, if you try to use the result of calling that function (e.g., assign it to a variable, or print it directly in an f-string like `print(f"Result: {my_function()}"))`, the result will be the special value `None`. This is Python's way of saying "this function completed its operations, but it didn't explicitly hand back any data."

* **When a function uses return with an argument (e.g., `return 10`, `return` `"hello"`, `return my_list`):**

  * You can call the function to make it perform actions.

  * Crucially, the function will stop executing at the `return` statement and will hand back the specific value you put after `return`.

  * You can then capture or use this returned value (e.g., `result = my_function()`, or `print(my_function()))`.
  <br>

**Analogy Recap:**

* **No** return: You tell a worker (function) to "Clean the car." They clean the car (perform actions), but they don't give you anything back. If you ask "What did you give me?", the answer is "Nothing" (Python's None).

* **With** return: You tell a worker (function) to "Go fetch the keys." They go get the keys (perform actions) and then they hand you the keys (return keys). Now you have the keys to use.








-------------------------------------------------

## Q: So one of the use case for function is to make some variable local and make them stop being global?

**A:** Yes, that's absolutely one of the core use cases and benefits of functions! 🎉

A primary reason to use a function is to **create a local scope**, which in turn allows you to define *local variables** that are confined to that function. This prevents them from cluttering the global namespace and avoids potential naming conflicts with other parts of your code.

Think of it like this:

* **Without functions (all global)**: Every tool you use in your workshop is just sitting out on one big workbench. If you have two different projects, and both need a "hammer," it can get messy and confusing which "hammer" belongs to which project.

* **With functions (local scope)**: Each project gets its own designated toolbox. When you work on "Project A," you open its toolbox, and any "hammer" inside that box belongs only to Project A. Once you close Project A's toolbox, those specific tools are put away. This means "Project B" can also have its own "hammer" in its own toolbox, and they won't conflict.

So, by using functions, you effectively encapsulate variables. They only exist and are accessible while the function is running, and then they're cleaned up. This makes your code much cleaner, more organized, and less prone to unexpected bugs from variables accidentally interfering with each other.


-------------------------------------------------

## Debugging

1. Describe the problem.
2.  Reproduce the bug:
  It simply means make the problem happen again on purpose. <br>
  Imagine your game crashed. To fix it, you need to figure out exactly what you did before it crashed so you can make it crash again. Once you can make it crash every time, you can then try to find out why it's crashing.
3. Play computer
4. Fix the errors (red underlines)
5. Use `print()`
6. Use a debugger : <br>
   [pythontutor](https://pythontutor.com/python-compiler.html).<br>
   Thonny app.

-------------------------------------------------


## Logging

### What is it?

**Logging** is a way for a computer program to record events as they happen. It's a structured way of keeping a history of what the program is doing, when it's doing it, and what the results are. These records are called **logs**.

### Levels of Logging

[Python Tutorial: Logging Basics](https://www.youtube.com/watch?v=-ARI4Cz-awo)


The `logging` module has different levels of severity, so you can decide how important a particular message is. This is a bit like having different colored sticky notes for different levels of urgency. The standard levels, in order from least to most severe, are:

* **DEBUG:** Detailed information, typically only of interest when diagnosing problems. Think of this as the most "chatty" level, for developers only. <br>
* **INFO:** Confirmation that things are working as expected. "The program started." <br>
* **WARNING:** An indication that something unexpected happened, or a potential problem in the near future. The software is still working as expected. "The file could not be found, but we'll create a new one." <br>
* **ERROR:** Due to a more serious problem, the software has not been able to perform some function. "Failed to connect to the database." <br>
* **CRITICAL:** A serious error, indicating that the program itself may be unable to continue running. "The server is shutting down." <br>

**Example:**
```python
import logging

# Configure the basic settings
logging.basicConfig(level=logging.INFO)

# Now you can use the logger
logging.debug('This is a debug message')
logging.info('This is an info message')
logging.warning('This is a warning message')
```


The **"default level for logging is set to WARNING,"**. it means that Python will only show you messages that are at the `WARNING` level or higher. <br>

So, if you write a log message with `logging.info("Everything is fine.")`, you won't see it on the screen because the default setting is to ignore "info" messages. But if you write `logging.warning("Something looks a bit off.")`, you will see that message because it's at the "warning" level. You'll also see `logging.error` and `logging.critical` messages.  <br>

Think of it as a filter. By default, the filter is set to "WARNING," so anything less important than a warning gets filtered out and you don't see it. This is useful because it keeps your program from showing you a huge wall of text with all the minor details, and it only shows you the things you should probably pay attention to.  <br>


## Understanding "WARNING level or higher"

The phrase **"WARNING level or higher"** means the logging system is configured to display messages with a severity of **`WARNING`**, **`ERROR`**, and **`CRITICAL`**. The term "higher" refers to the position on a hierarchy of logging levels, where each step up signifies a more serious issue.


### The Hierarchy of Logging Levels

Think of logging levels as a ladder 🪜. The higher a message is on the ladder, the more severe the issue it reports:<br>


* **`DEBUG`**: The lowest level, used for detailed information to help developers diagnose problems.<br>
* **`INFO`**: A general level for program progress updates.<br>
* **`WARNING`**: A step up, indicating an unexpected event or a potential problem. The program can usually still continue running.<br>
* **`ERROR`**: A serious problem has occurred, and the program could not perform a specific function.<br>
* **`CRITICAL`**: The highest and most severe level, indicating a serious error that may cause the program to shut down.<br>

When the logging level is set to `WARNING`, it acts like a filter. It allows all messages at the `WARNING` level and above to pass through, while blocking less severe messages like `INFO` and `DEBUG`. This helps you focus on important issues without being flooded with less critical information.


### How To Change The Default Level For Logging: 

```python
logging.basicConfig(level=logging.DEBUG)
```

### Basic File Logging
```python
import logging

# Configure logging to save to a file named 'app.log'
logging.basicConfig(filename='app.log', level=logging.INFO)

# These messages will be written to the 'app.log' file
logging.info('Application started.')
logging.warning('Something unexpected happened.')
```

After you run this script, you'll find a new file called app.log in the same directory as your script, containing the two log messages. Nothing will show up in your terminal because the messages are being written to the file.


### Standard `LogRecord` Attributes

* **`asctime`**: Human-readable time of the log creation (e.g., `'YYYY-MM-DD HH:MM:SS,sss'`).
* **`created`**: The time of creation as a Unix epoch timestamp (float).
* **`filename`**: The basename of the file where the logging call originated (e.g., `'my_module.py'`).
* **`funcName`**: The name of the function or method that made the log call.
* **`levelname`**: The text name of the logging level (e.g., `'INFO'`, `'WARNING'`).
* **`levelno`**: The numeric value of the logging level (e.g., `20` for `INFO`, `40` for `ERROR`).
* **`lineno`**: The line number in the source file where the logging call was made.
* **`module`**: The module name from the filename (e.g., `'my_module'`).
* **`msecs`**: The milliseconds component of the creation time.
* **`message`**: The final, formatted log message string.
* **`name`**: The name of the logger instance.
* **`pathname`**: The full path to the source file.
* **`process`**: The Process ID (PID).
* **`processName`**: The name of the current process.
* **`relativeCreated`**: The time in milliseconds since the logging system was initialized.
* **`thread`**: The thread ID.
* **`threadName`**: The name of the thread.


### 1. General Information

* **`name`**: The name of the logger instance (from `logging.getLogger()`).
    * **Description**: A string identifying the logger.
    * **Example**: `logging.getLogger('my_app')` sets this to `'my_app'`.
* **`levelno`**: The numeric value of the log level.
    * **Description**: An integer representing the log level (e.g., `20` for INFO, `40` for ERROR).
    * **Example**: `logging.INFO` corresponds to `20`.
* **`levelname`**: The textual name of the log level.
    * **Description**: A string representation of the log level (e.g., `'INFO'`, `'WARNING'`).
    * **Example**: `logging.INFO` sets this to `'INFO'`.
* **`pathname`**: The full path to the source file.
    * **Description**: The complete file path where the logging call was made.
    * **Example**: `'/path/to/your_project/module.py'`
* **`filename`**: The basename of the source file.
    * **Description**: A shortened version of `pathname` containing only the filename.
    * **Example**: `'module.py'`
* **`lineno`**: The line number in the source file.
    * **Description**: The exact line number of the code that triggered the log.
    * **Example**: `15`
* **`funcName`**: The name of the function or method.
    * **Description**: Identifies the specific function or method that made the log call.
    * **Example**: `'my_function'`
* **`module`**: The module name.
    * **Description**: The file name without the `.py` extension.
    * **Example**: `'module'`

---

### 2. Time and Process Information

* **`created`**: The creation time as a Unix timestamp.
    * **Description**: A floating-point number representing seconds since the epoch.
    * **Example**: `1631234567.890123`
* **`asctime`**: The human-readable creation time.
    * **Description**: Formatted time based on the `Formatter`'s `datefmt` (default is `YYYY-MM-DD HH:MM:SS,sss`).
    * **Example**: `'2025-09-07 21:20:06,123'`
* **`msecs`**: The millisecond portion of the creation time.
    * **Description**: The fractional part of the `created` attribute, in milliseconds.
    * **Example**: `123.456`
* **`relativeCreated`**: Time in milliseconds since the logging module was loaded.
    * **Description**: Useful for timing and performance analysis within an application run.
    * **Example**: `567.89` (milliseconds since startup)
* **`process`**: The ID of the current process.
    * **Description**: The Process ID (PID) of the Python process.
    * **Example**: `12345`
* **`processName`**: The name of the current process.
    * **Description**: The name of the process, if available.
    * **Example**: `'MainProcess'`
* **`thread`**: The ID of the current thread.
    * **Description**: The unique ID for the thread that made the log call.
    * **Example**: `987654321`
* **`threadName`**: The name of the current thread.
    * **Description**: The name given to the thread.
    * **Example**: `'MainThread'`

---

### 3. Message and Exception Information

* **`message`**: The formatted log message.
    * **Description**: The final string ready for output, with `msg` and `args` combined.
    * **Example**: `'User 'john' logged in.'`
* **`msg`**: The unformatted log message string.
    * **Description**: The original message string passed to the logger.
    * **Example**: `'User %s logged in.'`
* **`args`**: The arguments for message formatting.
    * **Description**: The tuple or dictionary of arguments passed with the log message.
    * **Example**: `('john',)` or `{'user': 'john'}`
* **`exc_info`**: A tuple of exception information.
    * **Description**: Contains `(type, value, traceback)` if an exception was logged.
    * **Example**: `(<class 'ZeroDivisionError'>, ZeroDivisionError('division by zero'), <traceback object at ...>)`
* **`exc_text`**: The formatted exception traceback string.
    * **Description**: The traceback formatted into a multi-line string.
    * **Example**: `Traceback (most recent call last):\n  File "...", line 10, in ...`
* **`stack_info`**: The formatted stack trace.
    * **Description**: Stack information if a stack trace was requested.
    * **Example**: `'Stack (most recent call last):\n  File "...", line 10, in ...'`


Example:

```python
import logging
import sys

# 1. Create a custom format string using the attributes listed above.
# We'll include the timestamp, log level, logger name,
# the file and line number, and the message itself.
log_format = "%(asctime)s - %(levelname)s - %(name)s - (%(filename)s:%(lineno)d) - %(message)s"

# 2. Create a Formatter object with the custom format.
formatter = logging.Formatter(log_format)

# 3. Create a StreamHandler to direct logs to the console (stdout).
stream_handler = logging.StreamHandler(sys.stdout)

# 4. Set the formatter for the handler.
stream_handler.setFormatter(formatter)

# 5. Get a logger instance.
logger = logging.getLogger("MyCustomApp")

# 6. Set the logging level for the logger.
logger.setLevel(logging.DEBUG)

# 7. Add the handler to the logger.
logger.addHandler(stream_handler)

# 8. Log some messages to see the custom format in action.
def my_function():
    """A sample function to demonstrate logging."""
    logger.info("This is an informational message.")
    logger.warning("This is a warning message.")
    logger.error("This is an error message!")

my_function()
```



-------------------------------------------------


## OOP  (Object-Oriented Programming) : 
In OOP we are trying to model  real life objects. <br>

Objects :
* Have things (Arttributes/Variables) : <br>
  is_holding_plate = True <br>
  tables = [4, 3 , 2]
* Do things. Like some kinda of functionality. (Methods) <br>
  def take_order(table, order) <br>

**An object** is basically combining a peice of data (attributes) and some kinda of functionality (methods). <br>
We can have multiple objects, generated from the same type. <br>

**Class , Object :** <br>
car = CarBlueprint() <br>
`car` is an object that is generetad from the `CarBlueprint()` class.


-------------------------------------------------
## Creating `classes`:

```python
class User:
    def __init__(self):
        pass
```

Example:

```python
class User:
    def __init__(self):
        print("New user has been created")
```

*Note:* 
<br>
The `__init__` method in a Python class is a special method that gets called automatically every single time you create a new object (or "instance") from that class.

```python
class User:
    def __init__(self):
        print("New user has been created")

user_1 = User() # __init__ called (1st time)
user_2 = User() # __init__ called (2nd time)
user_3 = User() # __init__ called (3rd time)
user_4 = User() # __init__ called (4th time)

# New user has been created
# New user has been created
# New user has been created
# New user has been created
```


This is why `__init__` is often called the constructor in other programming languages. Its main job is to initialize the attributes (the starting data) of the brand new object that's being created.
<br>

-------------------------------------------------

## `self.`:

**You need `self.` for an attribute when you want to access or change a value that is a permanent part of the object.**

You **don't** need `self.` when you are talking about a temporary value, like a parameter that was just passed into the method.<br>

We need to use `self` for an attribute when we want to make that attribute a part of the object itself. We don't need to use `self` when the attribute is a simple variable that only exists inside a function and disappears when the function is finished.


### What is `self.`?

Imagine you're building a robot. Each robot needs to have its own color, right? When you create a robot, you want to say, "This robot's color is red." The word `self` is like pointing to that specific robot and saying, "Hey, you (the robot), your color is red."

When you define an attribute like `self.color = "red"`, you are attaching the `color` attribute directly to the specific object you've created. This means every time you talk about that robot, you can ask it, "What's your color?" and it will remember.


### When to Use `self.`?
You should use `self` for an attribute when you want that attribute to be saved and remembered by the object. This is usually done inside the `__init__` function (the special function that runs when you create a new object).

For example, let's say you're building a Car class. Each `car` has a `brand` and a `color`. You want each car object to remember its own brand and color.

```python
class Car:
    def __init__(self, brand, color):
        # We use self here so that the object remembers its brand and color.
        self.brand = brand
        self.color = color

# Now we can create a car object.
my_car = Car("Honda", "blue")

# We can access the attributes we saved.
print(my_car.brand)  # Output: Honda
print(my_car.color)  # Output: blue
```

In this example, `my_car` is an object, and its `brand` is "Honda". If you create another car, `your_car`, its brand can be something different, like "Toyota". The `self` makes sure each car has its own brand and color.

### When to NOT Use `self.`:

You don't need to use `self` for an attribute if the attribute is just a temporary variable that's only needed for a little while, inside a specific function. Once the function is done, the variable is forgotten.<br>

Let's say you have a function inside your Car class that calculates a special code for the car, but you don't need the `car` to remember this code forever.

```python
class Car:
    def __init__(self, brand, color):
        self.brand = brand
        self.color = color

    def calculate_code(self):
        # 'temporary_code' is a simple variable, not an attribute of the object.
        # It's only needed inside this function and is forgotten afterwards.
        temporary_code = "XYZ-" + self.brand
        return temporary_code

my_car = Car("Honda", "blue")
car_code = my_car.calculate_code()

print(car_code)  # Output: XYZ-Honda
```

Here, `temporary_code` is not part of `self`. It's just a variable that's used to hold a value for a moment while the function is running. Once `calculate_code` is finished, `temporary_code` is gone. You can't say `my_car.temporary_code` because it doesn't belong to the car object.

-------------------------------------


## Class inheritance

it's a way for a new class to inherit or "borrow" properties (attributes) and behaviors (methods) from an existing class. <br>

Think of it like a family tree. A **parent class** (or **base class** or **superclass**) is like a parent. It has certain traits, like a last name or eye color. A **child class** (or **derived class** or **subclass**) is like a child. It can inherit those traits from the parent. <br>


Syntax :
```python
class Fish(Animal):
    def __init__(self):
        super().__init__()
```

This is our `Fish` class
```python
class Fish:
    def __init__(self):
```

For a class to inherit from another class, all we have to do is:
```python
class Fish(Animal):
    def __init__(self):
        super().__init__()
```

**What `super()` does**

The `super()` function is a special tool in Python that allows a child class to call a method from its parent class.<br>

*Note:* If you don't call `super().__init__()`, the child class's `__init__` method will completely override the parent's `__init__` method.



### Modifying a Method:

```python
class Animal:
    def __init__(self, name, animal_type):
        self.name = name
        self.animal_type = animal_type
        print(f"Say hello to {self.name}!")
        print(f"{self.name} is a {self.animal_type}")

    def sleep(self):
        print(f"{self.name} is currently sleeping")


dog = Animal("Rex", "dog")

print("---------------------------------------")

class Cat(Animal):
    def __init__(self, name, animal_type):
        super().__init__(name, animal_type)

    # Modifying the method
    def sleep(self):
        super().sleep()
        print(f"Wake {self.name} up!")


cat = Cat("Alex", "cat")
cat.sleep()
```

### Overriding a Method:

```python
class Animal:
    def __init__(self, name, animal_type):
        self.name = name
        self.animal_type = animal_type
        print(f"Say hello to {self.name}!")
        print(f"{self.name} is a {self.animal_type}")

    def sleep(self):
        print(f"{self.name} is currently sleeping")


dog = Animal("Rex", "dog")

print("---------------------------------------")

class Cat(Animal):
    def __init__(self, name, animal_type):
        super().__init__(name, animal_type)

    # Overriding a Method
    def sleep(self):
        print(f"Wake {self.name} up!")


cat = Cat("Alex", "cat")
cat.sleep()
```

-------------------------------------
## What Goes in the Main File?

**Import Statements:** All import statements, like from character import Character, belong here.

**Object Creation:** This is where you create all the objects from your classes, like player = Character(...) and enemy = Character(...).

**Game Logic:** This includes everything that controls the game's flow, like the while True game loop, the input() commands, and the if/else statements that decide what happens next.

**Calling Methods:** The main file's job is to call the methods of your objects, like player.attack(enemy).

Think of it like a movie: The classes are the actors—they know how to perform specific actions. The main file is the script and director—it tells the actors when to perform their actions and in what order.
















