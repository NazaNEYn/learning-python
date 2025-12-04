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

## What `split()` does:

`split(separator)` does two things:<br>

**1.** It uses the separator to decide where to cut the string:<br>
It looks for the separator and divides the string wherever it appears.

**2.** The separator itself does NOT appear in the result:<br>
So effectively yes, the separator disappears<br>
but only because it's used as a cutting point, not literally "deleted."

Example:

Here, I didn't specify any separator. So it'll seperate the string whenevr it finds an empty space because it's the default behavior.
```pytho
quotes = """
"Life is 10% what happens to us and 90% how we react to it." – Charles R. Swindoll

"You must do the things you think you cannot do." – Eleanor Roosevelt
"""
print(quotes.split())

# ['"Life', 'is', '10%', 'what', 'happens', 'to', 'us', 'and', '90%', 'how', 'we', 'react', 'to', 'it."', '–', 'Charles', 'R.', 'Swindoll', '"You', 'must', 'do', 'the', 'things', 'you', 'think', 'you', 'cannot', 'do."', '–', 'Eleanor', 'Roosevelt']
```

This one starts at each line break and since the string starts with line break, we get `''` as the first string in the list.
```python
quotes = """
"Life is 10% what happens to us and 90% how we react to it." – Charles R. Swindoll

"You must do the things you think you cannot do." – Eleanor Roosevelt
"""
print(quotes.split("\n"))

# ['', '"Life is 10% what happens to us and 90% how we react to it." – Charles R. Swindoll', '', '"You must do the things you think you cannot do." – Eleanor Roosevelt', '']
```

This one starts from two line breaks and it starts from the first quote.
```python
quotes = """
"Life is 10% what happens to us and 90% how we react to it." – Charles R. Swindoll

"You must do the things you think you cannot do." – Eleanor Roosevelt
"""
print(quotes.split("\n\n"))

# ['\n"Life is 10% what happens to us and 90% how we react to it." – Charles R. Swindoll', '"You must do the things you think you cannot do." – Eleanor Roosevelt\n']
```

```python
quotes = """
"Life is 10% what happens to us and 90% how we react to it." – Charles R. Swindoll

"You must do the things you think you cannot do." – Eleanor Roosevelt
"""
print(quotes.split("to"))

# ['\n"Life is 10% what happens ', ' us and 90% how we react ', ' it." – Charles R. Swindoll\n\n"You must do the things you think you cannot do." – Eleanor Roosevelt\n']
```




### 1. Splitting by space (default behavior):
By default, `split()` splits a string at spaces.

```python
text = "apple banana orange"
words = text.split()
print(words)

# ['apple', 'banana', 'orange']
```

### 2. Splitting by a specific character:
You can tell `split()` to break the string at a specific character, like a comma `,`, hyphen `-`, or any character you choose.

```python
text = "apple,banana,orange"
words = text.split(",")
print(words)

# ['apple', 'banana', 'orange']
```

```python
text = "apple-banana-orange"
words = text.split("-")
print(words)

# ['apple', 'banana', 'orange']
```

### 3. splitting with newlines (`\n`)

```python
text = """apple
banana
orange
grape"""
lines = text.split("\n")
print(lines)

# ['apple', 'banana', 'orange']
```


### 4. splitting in reverse order (`rsplit()`)

```python
text = "apple banana orange"
words = text.rsplit(" ", 1)
print(words)

# ['apple banana', 'orange']
```

------------------------

**Here are some more examples from my notebook:**

[LINK](https://static.marimo.app/static/split-vs-strip-ylc3)

------------------------

## (Learn later)
###  splitting with multiple separators:
`re.split()` method 

###  splitting with a limit (`maxsplit`)
