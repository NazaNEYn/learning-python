# Learnin Python


## Taking paython notes from [Dr. Angela Yu's](https://www.udemy.com/course/100-days-of-code/?srsltid=AfmBOoqVLnX2FVCJWsKZIQXpZmtsk2hJeZ4mki6rIAl8QL7ykq0aBmsq) course.

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





















