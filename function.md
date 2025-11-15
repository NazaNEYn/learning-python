## Function


```python
def name(args):
    pass
```

Example :

```python
def my_function():
    print("Hello")
    print("Bye")


my_function()

# Hello
# Bye
```


## Unlimited Positioal Arguments
```python
def add(*args):
    for n in args:
        print(n)
```


```python
def add(*args):
    sum = 0
    for n in args:
        sum += n
    return sum


print(add(5, 4, 3, 2, 8, 1, 11))
# 34
```

```python
def display_name(*args):
    for arg in args:
        print(arg, end=" ")


display_name("Naz", "Ash", "III")
# Naz Ash III
```

## `kwargs`: Keyword Arguments:

```python
def calculate(**kwargs):
    print(type(kwargs))


calculate(add=3, multiply=6)
# <class 'dict'>
```

```python
def calculate(**kwargs):
    for key, value in kwargs.items():
        print(key, value)


calculate(add=3, multiply=6)


# add 3
# multiply 6
```


```python
def address(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")


address(
    street="123 Fake St.", pobox="P.O Box 777", city="Detroit", state="MI", zip="54321"
)

# street: 123 Fake St.
# pobox: P.O Box 777
# city: Detroit
# state: MI
# zip: 54321
```

```python
def address(*args, **kwargs):
    for arg in args:
        print(arg, end=" ")
    print()
    for key, value in kwargs.items():
        print(f"{key}: {value}")

address(
    "Naz",
    "Ashrafi",
    street="123 Fake St.",
    pobox="P.O Box 777",
    city="Detroit",
    state="MI",
    zip="54321",
)

# Naz Ashrafi 
# street: 123 Fake St.
# pobox: P.O Box 777
# city: Detroit
# state: MI
# zip: 54321
```

```python
def calculate(**kwargs):
    print(kwargs["add"])
    print(kwargs["multiply"])


calculate(add=3, multiply=6)

# 3
# 6
```



```python
def calculate(n, **kwargs):
    n += kwargs["add"]
    n *= kwargs["multiply"]
    print(n)


calculate(2, add=3, multiply=6)

# 30
```

### Using `.get()` for Specific Values


```python
def address(*args, **kwargs):
    for arg in args:
        print(arg, end=" ")

    print()

    print(f"{kwargs.get("street")}")
    print(f"{kwargs.get("city")}, {kwargs.get("state")}, {kwargs.get("zip")}")


address(
    "Naz",
    "Ashrafi",
    street="123 Fake St.",
    city="Detroit",
    state="MI",
    zip="54321",
)

# Naz Ashrafi 
# 123 Fake St.
# Detroit, MI, 54321
```


*NOTE:*<br>

If we do this:
```python
def address(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")
```
It will get all of the arguments in kwargs but if we want to call some specific kwargs we use the `get()` method.

```python
print(f"{kwargs.get("street")}")
```
