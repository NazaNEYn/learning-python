# `strip()`: 
`strip()` removes **only whitespace** from the beginning and end of a string (not the middle).<br>
It's the most commonly used to remove spaces and newline characters.

### What `strip()` does:
* Removes spaces at the start
* Removes spaces at the end
* Removes \n, \t, etc.


```python
text = "         Hello Wordl jhdfjhsdfg"
clean_text = text.strip()
print(clean_text)

# Hello World jhdfjhsdfg
```

```python
text = "         Hello World \n"
clean_text = text.strip()
print(clean_text)

# Hello World
```

------

# `split()`: 
`split()` takes a string and cuts it into a list based on a separator you choose.

### What `split()` does:
* Breaks the string wherever it finds the separator.
* Returns a list
