| Keyword | Purpose |
| :--- | :--- |
| **try** | The block of code following `try` is the critical operation. Python attempts to execute this code. If an exception occurs here, the execution immediately stops, and Python looks for a matching `except` block. |
| **except** | The block of code following `except` is the exception handler. It executes only if an exception occurs in the preceding `try` block. You can specify which type of exception you want to catch (e.g., `except ZeroDivisionError:`). |
| **else** | The code block following `else` executes only if the `try` block completes without any exceptions. |
| **finally** | The code block following `finally` will **always** execute, regardless of whether an exception occurred in the `try` block or not, and whether it was handled or not. It's often used for cleanup actions, like closing a file or network connection. |

```python
try:
    # Code that might cause an exception
    result = 10 / num
except ZeroDivisionError as e:
    # Code to handle a specific exception (ZeroDivisionError)
    print(f"Error: Cannot divide by zero. Details: {e}")
except (TypeError, ValueError):
    # Code to handle multiple specific exceptions
    print("Error: Invalid type or value provided.")
except Exception as e:
    # Code to handle any other unexpected exceptions (broad catch)
    print(f"An unexpected error occurred: {e}")
else:
    # Code to run IF the 'try' block was successful
    print(f"Division successful. Result: {result}")
finally:
    # Code that always runs (e.g., resource cleanup)
    print("Execution of the try/except block is complete.")
```

# Common Python Exceptions

| Exception Name | Meaning | Common Cause |
| :--- | :--- | :--- |
| **NameError** | A variable, function, or module name was used but hasn't been defined (or was misspelled). | Trying to access a variable before it's been assigned a value, or calling a function with a typo. |
| **TypeError** | An operation or function is applied to an object of an inappropriate type. | Attempting to add a string and an integer (`"hello" + 5`), or calling a method that doesn't exist on an object. |
| **ValueError** | A function receives an argument of the correct type, but an inappropriate value. | Trying to convert a non-numeric string into an integer: `int("abc")`. |
| **IndexError** | You tried to access an element in a sequence (like a list or tuple) using an index that is out of range. | Accessing `my_list[5]` when `my_list` only has 3 elements (indices 0, 1, 2). |
| **KeyError** | You tried to access a dictionary element using a key that doesn't exist in the dictionary. | Accessing `my_dict['age']` when the dictionary only contains the key `'name'`. |
| **ZeroDivisionError** | The second operand in a division or modulo operation is zero. | Trying to calculate `10 / 0`. |
| **FileNotFoundError** | An attempt to open a file or directory failed because it doesn't exist. | Using `open('missing_file.txt', 'r')` when the file isn't in the expected path. |
| **IndentationError** | Code is improperly indented, which violates Python's syntax rules. (While often treated like a syntax error by the parser, it specifically relates to runtime structure.) | Mixing spaces and tabs, or using incorrect indentation after a colon (`:`). |
| **AttributeError** | An attempt was made to access an attribute (property or method) that doesn't exist on an object. | Trying to call `my_list.add(1)` when the correct method is `my_list.append(1)`. |


**1. `NameError`**:

```python
try:
    first_name = "Naz"
    print(last_name)
except NameError as e:
    print(f"{e}")

# name 'last_name' is not defined
```

**2. `TypeError`**:

```python
try:
    num1 = 5
    num2 = "5"
    total = num1 + num2
    print(total)
except TypeError as e:
    print(f"Error: {e}")

# Error: unsupported operand type(s) for +: 'int' and 'str'
```

**3. `TypeError`**:

```python
try:
    user_input = int(input("What is your name?\n"))
    print(user_input)
except ValueError as e:
    print(f"{e}")

# If you dont enter a number as an input, you'll get an error
#  invalid literal for int() with base 10: 'ss'
```


**4. `IndexError`**:

```python
try:
    my_list = [1, 2, 3]
    print(my_list[3])
except IndexError as e:
    print(f"{e}")
# list index out of range
```



**5. `KeyError`**:

```python
dict = {
    "name": "Naz",
    "age": 32,
}

try:
    print(dict["naaame"])
except KeyError as e:
    print(f"{e} doesn't exist in the dictionary")

# 'naaame' doesn't exist in the dictionary
```

**6. `FileNotFoundError`**:

```python
filename = "non_existent_file.log"
try:
    with open(filename, 'r') as file:
        content = file.read()
except FileNotFoundError:
    print(f"Caught a FileNotFoundError! The file '{filename}' could not be found.")
    # A common recovery action is to create the file or use a default
    with open(filename, 'w') as file:
        file.write("Log file created.")
    print("New log file created successfully.")
```



