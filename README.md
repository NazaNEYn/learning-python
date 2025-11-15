
# Table of Contents


* [Printing outputs](#printing-outputs)
    * [String Concatenation (Combining Strings)](#string-concatenation-combining-strings)
* [Input Function](#input-function)
* [Variables](#variables)
* [Dat Types](#dat-types)
* [Subscripting](#subscripting)
* [Integer (Whole Number)](#integer-whole-number)
    * [Large Integer](#large-integer)
* [Float = Floating point number](#float--floating-point-number)
* [Boolean](#boolean)
* [Type Conversion Functions (Type casting)](#type-conversion-functions-type-casting)
* [Modulo Operator (`%`)](#modulo-operator-)
* [Condituinal Statement (`if / else`)](#condituinal-statement-if--else)
* [Nested `if / else`](#nested-if--else)
* [`if / elif/ else`](#if--elif-else)
* [Multiple if](#multiple-if)
* [Logocal Operators](#logocal-operators)
* [Random Module](#random-module)
* [Lists](#lists)
* [Tuple :](#tuple-)
* [constant :](#constant-)
* [For Loop](#for-loop)
* [Function](#function)
* [While Loop](#while-loop)
* [Slicing:](#slicing)
* [`return` keyword :](#return-keyword-)
    * [When we don't use return in a function](#when-we-dont-use-return-in-a-function-we-cant-just-call-the-function-and-expect-to-get-an-output-but-when-we-use-return-and-if-we-call-the-fucntion-well-get-an-output-right)
    * [Q: So one of the use case for function is to make some variable local and make them stop being global?](#q-so-one-of-the-use-case-for-function-is-to-make-some-variable-local-and-make-them-stop-being-global)
* [Debugging](#debugging)
* [`if __name__ == '__main__'`](#if-__name__-==-'__main__')
* [`async` and `await`](#async-and-await)
* [The `splat` or `unpacking` operator (`*`):](#the-splat-or-unpacking-operator-)
* [Ternary Operator](#ternary-operator)

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


## Unlimited Positioal Arguments
```python
def add(*args):
    for n in args:
        print(n)
```


```python
def add(*args):
    sum = 0
    for n in args:
        sum += n
    return sum


print(add(5, 4, 3, 2, 8, 1, 11))
# 34
```

```python
def display_name(*args):
    for arg in args:
        print(arg, end=" ")


display_name("Naz", "Ash", "III")
# Naz Ash III
```

## `kwargs`: Keyword Arguments:

```python
def calculate(**kwargs):
    print(type(kwargs))


calculate(add=3, multiply=6)
# <class 'dict'>
```

```python
def calculate(**kwargs):
    for key, value in kwargs.items():
        print(key, value)


calculate(add=3, multiply=6)


# add 3
# multiply 6
```


```python
def address(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")


address(
    street="123 Fake St.", pobox="P.O Box 777", city="Detroit", state="MI", zip="54321"
)

# street: 123 Fake St.
# pobox: P.O Box 777
# city: Detroit
# state: MI
# zip: 54321
```

```python
def address(*args, **kwargs):
    for arg in args:
        print(arg, end=" ")
    print()
    for key, value in kwargs.items():
        print(f"{key}: {value}")

address(
    "Naz",
    "Ashrafi",
    street="123 Fake St.",
    pobox="P.O Box 777",
    city="Detroit",
    state="MI",
    zip="54321",
)

# Naz Ashrafi 
# street: 123 Fake St.
# pobox: P.O Box 777
# city: Detroit
# state: MI
# zip: 54321
```

```python
def calculate(**kwargs):
    print(kwargs["add"])
    print(kwargs["multiply"])


calculate(add=3, multiply=6)

# 3
# 6
```



```python
def calculate(n, **kwargs):
    n += kwargs["add"]
    n *= kwargs["multiply"]
    print(n)


calculate(2, add=3, multiply=6)

# 30
```

### Using `.get()` for Specific Values


```python
def address(*args, **kwargs):
    for arg in args:
        print(arg, end=" ")

    print()

    print(f"{kwargs.get("street")}")
    print(f"{kwargs.get("city")}, {kwargs.get("state")}, {kwargs.get("zip")}")


address(
    "Naz",
    "Ashrafi",
    street="123 Fake St.",
    city="Detroit",
    state="MI",
    zip="54321",
)

# Naz Ashrafi 
# 123 Fake St.
# Detroit, MI, 54321
```


*NOTE:*<br>

If we do this:
```python
def address(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")
```
It will get all of the arguments in kwargs but if we want to call some specific kwargs we use the `get()` method.

```python
print(f"{kwargs.get("street")}")
```
    
----------------------------------------------
## While Loop


```python
while something_is_true:
    # Do something 
    # The loop will stop hen something becomes false
```

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

## List Comprehension
It is designed to build a brand new list.

**`for loop`**
```python
numbers = [1, 2, 3]
new_list = []

for n in numbers:
    add_1 = n + 1
    new_list.append(add_1)
```


**`List comprehension`**
```python
new_list = [new_item for item in list]
```

```python
numbers = [1, 2, 3]
new_list = [n + 1 for n in numbers]
# list ==> numbers
# item ==> n
# new_item ==> n + 1
```

```python
new_list = [number * 2 for number in range(1, 5)]
```
---------------------------------------------

## Conditionnel List Comprehension:

```python
new_list = [new_item for item in list if test]
```

```python
names = ["Max", "Ashley", "lexa", "Alex", "Roxy", "Alison"]

new_list = [name for name in names if name[0] == "A"]
print(new_list)
# ['Ashley', 'Alex', 'Alison']
```
----------------------------------------------

## Dictionary Comprehension

```python
new_dict = {new_key:new_value for item in list}

new_dict = {new_key:new_value for (key, value) in dict.items()}

new_dict = {new_key:new_value for (key, value) in dict.items() if test}
```

```python
students = ["Alex", "Max", "Ashley", "Rachel", "Chad"]

scores = {name: random.randint(1, 100) for name in students}

print(scores)

# {'Alex': 85, 'Max': 44, 'Ashley': 88, 'Rachel': 11, 'Chad': 11}
```

```python
students = ["Alex", "Max", "Ashley", "Rachel", "Chad"]

scores = {
    name: random.randint(1, 100) for name in students if random.randint(1, 100) > 80
}
print(scores)

passed_students = {name: score for (name, score) in scores.items() if score >= 60}
print(passed_students)

# {'Max': 39, 'Ashley': 25, 'Rachel': 18, 'Chad': 88}
# {'Chad': 88}
```



---------------------------------------------

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

## `if __name__ == '__main__'`






--------

## `async` and `await`

`async` is short for **asynchronous**. It tells Python that a function can be run alongside other code, instead of having to wait for it to finish. <br>

Imagine you're at a coffee shop. When you place your order, you don't just stand there staring at the barista until your coffee is done, right? You might go find a table, check your phone, or chat with a friend. `async` is like that. It lets your program place a "request" (like an API call that takes time) and then move on to do other things while it waits for the result. When the result is ready, the program comes back and continues from where it left off. This makes your program much more efficient. The `await` keyword is used to tell the program to wait for the result of an asynchronous task before moving on. <br>

You can think of the `async function` as politely stepping aside to let other functions run, and then it picks up where it left off once the task it was waiting for is complete. This is the core of what makes your code efficient and responsive. <br>

`async` and `await` work together. You can't use one without the other. <br>

Think of it like this:

* `async` is the label you put on a function to tell Python, "This function might have a part that needs to wait for something. It can step aside to let other code run while it waits."
* `await` is the specific instruction inside an `async` function that tells the program, "Okay, pause right here and wait for this one thing to finish. While you're waiting, go do something else."
<br>

You must define a function as `async` to be able to use the `await` keyword inside it. If you try to use `await in a regular function, you'll get an error. They are a team! 

-----------------------


## The `splat` or `unpacking` operator (`*`):

Let's say you have list of tuples and want to create a random shape size for turtle module:
```python
SHAPE_SIZE = [(1,4),(1,5),(1,6)]
random_size = random.choice(SHAPE_SIZE)
```

You can't just use the `random_size` for `shapesize()` because it accept a tuple.
```python
self.shapesize(random_size)
```

So we need to use the  `*` (splat) operator.
```pyhon
self.shapesize(*random_size)
```

The asterisk `*` operator is the key to solving this. When you place a `*` in front of an iterable (like your `random_size` tuple), it unpacks the elements of that iterable and passes them to the function as separate, individual arguments. <br>

By adding the `*` before `random_size`, you're telling Python to take the chosen tuple (e.g., `(1, 4)`) and pass its elements as `shapesize(1, 4)`. This is what the `shapesize()` method expects and will allow your code to work correctly.


---------------------------

## Ternary Operator

**Ternary Syntax** <br>
The general format is:
```python
value_if_true if condition else value_if_false
```

Example:
```python
if self.ycor() > FINISH_LINE_Y:
            return True
        else:
            return False
```

```python
       # Ternary Form
        return True if self.ycor() > FINISH_LINE_Y else False
    
        # a simpler and more Pythonic way
        return self.ycor() > FINISH_LINE_Y
```


--------------------------
