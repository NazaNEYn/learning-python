| Keyword | Purpose |
| :--- | :--- |
| **try** (or **TRY**) | Encloses the code that might cause an exception. |
| **except** (or **catch**) | Specifies the code to be executed when a particular exception type is raised in the try block. |
| **finally** (or **FINALLY**) | Specifies code that will always be executed, regardless of whether an exception occurred or was handled. Useful for cleanup actions (e.g., closing files or releasing resources). |
| **raise** (or **throw**) | Used to manually trigger an exception if a certain condition is met in your code. |

```python
try:
    # 1. Code that might raise an exception
    numerator = 10
    denominator = 0
    result = numerator / denominator  # This will raise a ZeroDivisionError
    
except ZeroDivisionError:
    # 2. Code to run ONLY if a ZeroDivisionError occurs
    print("Error: Cannot divide by zero. Please check the input.")
    
except Exception as e:
    # 3. Code to run for any OTHER exception (catches all)
    print(f"An unexpected error occurred: {e}")
    
else:
    # 4. Code to run ONLY IF the 'try' block completes without an exception
    print("Division was successful!")
    print(f"Result: {result}")
    
finally:
    # 5. Code that ALWAYS runs, no matter what
    print("Execution attempt finished.")
```
