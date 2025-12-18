# Program Memory (RAM)
Program memory is what your code uses while it is running.<br>

Examples:
```python
movies = []
movie = {"title": "Avatar"}
rank = 1
```


**Key properties of program memory**

* Lives in RAM
* Exists only while the program is running
* Is destroyed when the program ends
* Fast
* Temporary

**What happens when your script stops?**<br>
Everything is gone.
```text
Program ends → RAM cleared → variables vanish
```

**Analogy**<br>
Program memory is like:
* Notes written on a whiteboard
* When you leave the room, they’re erased


# Persistent Storage (Disk)
Persistent storage is anything saved to disk.<br>

Examples:
* `.json`
* `.txt`
* `.csv`
* `.db`
* Images, videos, etc.
* ```python
  json.dump(movies, file)
  ```

**Key properties of persistent storage**
* Lives on disk
* Survives program restarts
* Slower than RAM
* Durable
* Shareable between programs

**What happens when your script stops?**<br>
Nothing. The file stays.

**Analogy**<br>
Persistent storage is like:
* Writing in a notebook
* Closing the notebook doesn’t erase it
