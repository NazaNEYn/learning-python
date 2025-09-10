# Logging


### What is it?

**Logging** is a way for a computer program to record events as they happen. It's a structured way of keeping a history of what the program is doing, when it's doing it, and what the results are. These records are called **logs**.

### Levels of Logging




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

### When to Use Each Logging Level

Deciding which logging level to use depends on the type of event that is happening in your program. Think of each level as a different kind of note you would take for your own records or for another developer.

Here’s a simple guide for when to use each level:

---

#### `INFO`

Use `logging.info()` for routine operations and milestones. These are events that confirm your code is running as expected and are helpful for tracking its progress. They are not errors, but you want to know they happened.

* **Example:**
  * A user successfully logs in.
  * A database connection is established.
  * A query completes successfully. ⬅️ This is why info was used in the statistics code. The messages confirm that the connection and queries worked as they should.

---

#### `DEBUG`

Use `logging.debug()` for detailed, low-level events that are only useful for debugging. These messages are typically too verbose to be shown during normal operation but are invaluable when trying to pinpoint exactly where a problem is occurring.

* **Example:**
  * The value of a variable at a specific point in a function.
  * The exact parameters being passed to a function.
  * A step-by-step breakdown of a complex algorithm.

---

#### `WARNING`

Use `logging.warning()` for unexpected but non-critical events. These messages alert you to potential problems that don't stop the program from running but might cause issues later.

* **Example:**
  * A file is not found, so the program falls back to a default setting.
  * A function receives an invalid input, but it can still produce a reasonable output.
  * A network request takes longer than expected.

---

#### `ERROR`

Use `logging.error()` for serious errors where the program fails to perform a function. The program may continue to run, but the specific task could not be completed.

* **Example:**
  * A database query fails due to a syntax error.
  * An API request returns an error.
  * A critical file cannot be written to or read from.

---

#### `CRITICAL`

Use `logging.critical()` for severe errors that are likely to cause the program to crash or become unusable. This level is for emergencies that require immediate attention.

* **Example:**
  * A database connection cannot be established, and the entire application depends on it.
  * An essential dependency fails to load, preventing the program from starting.

---


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


Example 1:

```python
import logging

logging.basicConfig(
    filename='my_app.log', 
    level=logging.INFO, 
    format='%(asctime)s - %(levelname)s - %(message)s'
)

# Your logging messages from the last exercise
logging.info("Application started.")
logging.error("An error has occurred!")
```

Example 2:


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

### What is the Root Logger?

The **root logger** is a special logger at the top of the logging hierarchy. All other loggers you create are children of the root logger and inherit its settings by default.<br>

Think of it like the main folder on your computer. If you set a security policy on the main folder (e.g., only "read-only" access), all the subfolders inside it will inherit that policy unless you specifically change their individual settings. In logging, the root logger's settings—such as the logging level or where the output goes—are the "policy" that gets passed down.



### Logger

In Python's logging system, the root logger is the main, default logger, while a logger is a custom, named instance. All loggers, unless you specify otherwise, are children of the root logger, inheriting its settings like the logging level and handlers.

### What is a Logger?

A **logger** is the main object used to send log messages from an application. You typically create one for a specific part of your code, such as a module or class, and give it a descriptive name.

### How to Get a Logger

You get a logger instance by calling `logging.getLogger()`. It's a common practice to name your loggers after the module they are in, like `logging.getLogger(__name__)`. This allows you to configure specific loggers later on. <br>

The `getLogger()` function is designed to be idempotent. If you call it with the same name multiple times, it will always return the exact same logger object, preventing you from accidentally creating duplicate loggers.<br>


*Note 1:* The special variable `__name__` is a built-in Python variable that holds the name of the current module. Python automatically sets its value based on how you run your code.<br>
*Note 2:* It's best practice for naming logger is to use `__name__` instead of hardcoding a name.


### Logger Hierarchy

By default, a logger inherits its settings from its parent. All loggers ultimately inherit from the **root logger**, which is the top-level parent.<br>


Example:
```python
import logging

# This creates a custom logger named 'my_app'
app_logger = logging.getLogger('my_app')

# This message is sent through the 'my_app' logger
app_logger.info("This is a log message from my_app.")
```


### Why Do We Get a Logger?

Instead of just using `logging.info()` and `logging.warning()` everywhere, which all use the same default "root" logger, `getLogger()` allows you to create your own specific logger. This is great for a couple of reasons:

* **Organization:** You can name your loggers to match the different parts of your program. For example, if you have a file that handles a database, you could get a logger named `'database_handler'`.
* **Control:** This lets you configure each part of your program's logging differently. Maybe you want to see detailed `DEBUG` messages from your database code, but only `WARNING` messages from the rest of your app. You can do this by getting a specific logger and setting its level. <br>


Example:
```python
import logging

# This gets a logger specifically for the "payment" part of your code
payment_logger = logging.getLogger('payment')

# This gets a logger for the "shipping" part
shipping_logger = logging.getLogger('shipping')

# Now you can use them to send messages
payment_logger.info("Processing payment for order 123.")
shipping_logger.warning("Shipping address is missing zip code.")
```

If you call `logging.getLogger('payment')` in another file, you'll still get the exact same logger object. This means all log messages for the `'payment'` logger, no matter where they come from in your code, will go through the same configured logger. This is why it's a powerful way to manage your logs.

### Loggers, Handlers, and Formatters

Example: 

```python
logger = logging.getLogger(__name__)
logger.setLevel(logging.DEBUG)

log_format = logging.Formatter("%(levelname)s - %(asctime)s - %(name)s - %(message)s")

file_handler = logging.FileHandler("test.log")
file_handler.setFormatter(log_format)

logger.addHandler(file_handler)


def divide(num_1, num_2):
    logger.info(f"Dividing numbers: {num_1} / {num_2}")
    return num_1 / num_2
```

Let's analyze the code: <br>

**1. Creating the Logger**
```python
logger = logging.getLogger(__name__)
logger.setLevel(logging.DEBUG)
```
First, you create a custom logger. The `logging.getLogger(__name__)` line creates a new logger that is named after the current module (the file it's in). This is a best practice because it helps you identify where log messages are coming from in a large application.<br>

Next, you set the logger's level to `DEBUG`. This is the most important part of this section. It means the logger will process all messages at the `DEBUG` level and higher. Without this line, the logger would default to `WARNING` and ignore any `INFO` or `DEBUG` messages.<br>



**2. Creating the Formatter**
```python
log_format = logging.Formatter("%(levelname)s - %(asctime)s - %(name)s - %(message)s")
```

This line creates a `Formatter` object. A formatter is like a template for your log messages. The string inside the parentheses defines the exact layout for each log entry.

* `%(levelname)s`: The log message level (e.g., `DEBUG`, `INFO`).
* `%(asctime)s`: The timestamp of the log message.
* `%(name)s`: The name of the logger (in this case, the name of your file).
* `%(message)s`: The actual message text.



**3. Creating and Configuring the Handler**
```python
file_handler = logging.FileHandler("test.log")
file_handler.setFormatter(log_format)
```

Here, you create a `FileHandler`, which is an object that tells the logger to send messages to a specific file. The `FileHandler("test.log")` part creates a handler that'll write messages to a file named `test.log`. <br>

The next line, `file_handler.setFormatter(log_format)`, links the handler to the formatter you created. This ensures that every log message written to the `test.log` file will follow the specific format you defined. <br>



**4. Adding the Handler to the Logger**
```python
logger.addHandler(file_handler)
```

Finally, you **connect the handler to the logger**. By using `logger.addHandler()`, you are telling your custom logger to start sending all the messages it receives to the `file_handler`.<br>


After these steps, any logging call made through this `logger` object will now be written to the `test.log file with the custom format.

```python
def divide(num_1, num_2):
    logger.info(f"Dividing numbers: {num_1} / {num_2}")
    return num_1 / num_2
```




<hr>


### Youtube Video :
[Python Tutorial: Logging Basics](https://www.youtube.com/watch?v=-ARI4Cz-awo)
<br>
[Python Tutorial: Logging Advanced](https://www.youtube.com/watch?v=jxmzY9soFXg)

