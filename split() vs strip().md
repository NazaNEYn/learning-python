# `strip()`: CLEAN the ends
`strip()` removes **only whitespace** from the beginning and end of a string (not the middle).

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
