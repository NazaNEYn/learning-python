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
