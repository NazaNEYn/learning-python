# Learnin Python


## Taking paython notes from [Dr. Angela Yu's](https://www.udemy.com/course/100-days-of-code/?srsltid=AfmBOoqVLnX2FVCJWsKZIQXpZmtsk2hJeZ4mki6rIAl8QL7ykq0aBmsq) course.

--------------------------------
## Printing outputs : <br>
```python
print("Hello World!")
```
<br>
Instead of writing multiple lines like

```python
print("Hello World!")
print("Hello World!")
print("Hello World!")
```

We could write 
```python
print("Hello World! \nHello World! \nHello World")

# Hello World 
# Hello World 
# Hello World
```

### String Concatenation (Combining Strings)

```python
# Hello Naz

# We could add an empty strng in between the words :
print("Hello" + " " + "Naz")

# or
print("Hello " + "Naz")
# Hello Naz

# or
print("Hello" + " Naz")
# Hello Naz
```

----------------------------------------------
## Input Function

```python
input("A prompt for the user")
```
Example:

```python
input("What is your name?")
```


```python
print("Hello " + input("What is your name?") + "!")
```

----------------------------------------------

## Variables 
Variable is somtheing that can be changed or varied.

```python
name = input("What is your name?")
print(name)
```

----------------------------------------------


## Dat Types

1. String
2. Integer
3. Float
4. Boolean

----------------------------------------------


## Subscripting

Pulling out a particular element from a string and the number between square brackets determines which character you're going to pull out

```python
print("Hello"[0])

# H
```

* Tip :
We can use `-` and get the last character

```python
print("Hello"[-1])

# o
```

----------------------------------------------

## Integer (Whole Number)

```python
print(123 + 456)

# 468
```

## Large Integer 

For writing big numbers like 123,456,786 we use `_` instead of `,`
```python
print(123_456_789)

# 123456789
```
----------------------------------------------

## Float = Floating point number

```python
print(3.14159)

# 3.14159
```

----------------------------------------------
