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

## (Learn later)
###  splitting with multiple separators:
`re.split()` method 

###  splitting with a limit (`maxsplit`)
