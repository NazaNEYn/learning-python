## `datetime` Module Class Reference

This table summarizes the core classes, their attributes, and common methods within the Python `datetime` module.

| Class | Attributes | Common Methods | Description |
| :--- | :--- | :--- | :--- |
| **`date`** | `year`, `month`, `day` | `today()`, `fromtimestamp()`, `fromordinal()`, `isoformat()`, `ctime()`, `weekday()`, `isoweekday()`, `replace()`, `timetuple()` | Represents a calendar date (year, month, day). |
| **`time`** | `hour`, `minute`, `second`, `microsecond`, `tzinfo`, `fold` | `isoformat()`, `replace()`, `strftime(format)` | Represents a time of day independent of any particular day. |
| **`datetime`** | Inherits from `date`, adds `hour`, `minute`, `second`, `microsecond`, `tzinfo` | `now(tz=None)`, `utcnow()`, `fromtimestamp()`, `fromordinal()`, `combine(date, time)`, `strftime(format)`, `strptime(date_string, format)`, `replace()`, `isoformat()`, `timestamp()`, `timetuple()` | Combines date and time into a single object. |
| **`timedelta`** | `days`, `seconds`, `microseconds` | Supports arithmetic: `+`, `-`, `*`, `//`, `abs()`, `total_seconds()` | Represents a duration, difference between two dates or times. |
| **`tzinfo`** | Abstract base class; no direct attributes | `utcoffset(dt)`, `dst(dt)`, `tzname(dt)`, `fromutc(dt)` | Base class for dealing with time zones. |
| **`timezone`** | `utcoffset`, `tzname`, `dst` | `fromutc(dt)`, `utcoffset(dt)`, `tzname(dt)`, `dst(dt)` | Implements fixed offset time zones derived from `tzinfo`. |
| `datetime.MINYEAR` | Constant = 1 | N/A | Smallest year allowed in `date` or `datetime`. |
| `datetime.MAXYEAR` | Constant = 9999 | N/A | Largest year allowed in `date` or `datetime`. |

------


## Common `strftime` Formatting Codes

| Directive | Meaning |
| :--- | :--- |
| **`%Y`** | Year with century (e.g., **2025**) |
| **`%m`** | Month as zero-padded decimal (01-12) |
| **`%d`** | Day of the month (01-31) |
| **`%H`** | Hour (00-23) |
| **`%M`** | Minute (00-59) |
| **`%S`** | Second (00-59) |

-----

## `datetime.now()` Attributes and Methods

## ⚙️ Core Attributes and Methods of the `datetime` Object

This table details the common attributes and methods available on a `datetime` object (often referenced here as `now`).

| Attribute / Method | Type / Return | Description |
| :--- | :--- | :--- |
| **`now.year`** | `int` | Year (e.g., **2025**) |
| **`now.month`** | `int` | Month (**1–12**) |
| **`now.day`** | `int` | Day of the month (**1–31**) |
| **`now.hour`** | `int` | Hour of the day (**0–23**) |
| **`now.minute`** | `int` | Minute of the hour (**0–59**) |
| **`now.second`** | `int` | Second of the minute (**0–59**) |
| **`now.microsecond`** | `int` | Microsecond of the second (**0–999999**) |
| `now.tzinfo` | `tzinfo` or `None` | **Timezone info** (`None` if naive datetime) |
| `now.fold` | `int` (0 or 1) | Helps disambiguate during **DST transitions** (Python 3.6+) |
| --- | --- | --- |
| `now.date()` | `date` object | Returns the **date** part of the datetime |
| `now.time()` | `time` object | Returns the **time** part of the datetime |
| `now.timetz()` | `time` object | Returns the time with `tzinfo` |
| `now.replace(**kwargs)` | `datetime` object | Return a new datetime with **replaced components** |
| `now.timetuple()` | `time.struct_time` | Returns a **`struct_time` tuple** for use with `time` module |
| `now.utctimetuple()` | `time.struct_time` | Returns **UTC `struct_time`** |
| `now.toordinal()` | `int` | Returns the **proleptic Gregorian ordinal** (days since 1 Jan 1) |
| `now.timestamp()` | `float` | Returns **POSIX timestamp** (seconds since epoch) |
| `now.weekday()` | `int` | Day of the week (**Monday = 0 … Sunday = 6**) |
| `now.isoweekday()` | `int` | Day of the week (**Monday = 1 … Sunday = 7**) |
| `now.isoformat()` | `str` | Returns **ISO 8601** formatted string (YYYY-MM-DDTHH:MM:SS.mmmmmm) |
| `now.ctime()` | `str` | Returns a string like `Tue Dec 2 20:45:00 2025` |
| `now.strftime(format)` | `str` | **Format datetime as string** according to format codes |
| `now.strptime(date_string, format)` | `datetime` object | **Parse string to datetime** (class method) |
| `now.astimezone(tz=None)` | `datetime` object | **Convert to given timezone**; if `tz=None`, convert to local timezone |
| --- | --- | --- |
| `datetime.fromtimestamp(timestamp, tz=None)` | `datetime` object | **Class method**: create datetime from POSIX timestamp |
| `datetime.utcnow()` | `datetime` object | **Class method**: current UTC datetime (**naive**) |
| `datetime.now(tz=None)` | `datetime` object | **Class method**: current local datetime, optionally with `tzinfo` |


```python
import datetime as dt

# First get the `now` class and then you can get the year, month etc
now = dt.datetime.now()
year = now.year
month = now.month
day = now.day

print(day)


date_of_birth = dt.datetime(year=1990, month=1, day=5)
print(date_of_birth)
# 1990-01-05 00:00:00
```
