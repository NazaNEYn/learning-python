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

