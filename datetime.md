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
