 ## Dictionary


```python
dictionary = {
    "key": "value",
}
```

Example:

```python
bio = {
    "name": "naz",
    "age": 31,
}

# {'name': 'naz', 'age': 31}
```

## Assigning a new key

```python
bio["is_employed"] = True
# {'name': 'naz', 'age': 31, 'is_employed': True}
```

## Reassigning a new key

```python
bio = {
    "name": "naz",
    "age": 31,
}

bio["name"] = "Ash"

# {'name': 'Ash', 'age': 31}
```

## Wiping/deleting the dictionary 

```python
bio = {
    "name": "naz",
    "age": 31,
}

bio = {}

# {}

# {'name': 'Ash', 'age': 31}
```


 ## Nesting lists inside a dictionary


```python
bio = {
    "name": ["Ash", "Max", "Naz"],
    "age": 31,
}

bio = {
    "name": ["Ash", "Max", "Naz", ["Alex", "John"]],
    "age": 31,
} 
```

### How to print out the values inside the nested lists?


```python
bio = {
    "name": ["Ash", "Max", "Naz"],
    "age": 31,
}

print(bio["name"][1])
# Max
```

```python
bio = {
    "name": ["Ash", "Max", "Naz", ["Alex", "John"]],
    "age": 31,
}

print(bio["name"][3][1])
# John 
```


 ## A nested dictionary


```python
user_profile = {
    "name": "Alex",
    "contact": {
        "email": "alex@example.com",
        "phone": "123-456-7890",
    },
    "status": "Active",
}


print(user_profile["contact"]["phone"])
# 123-456-7890
```
----------------------------------------------

 ## How to loop through a dictionary

When we loop through a dictionary, it loops through the `keys.

In this example each fruit is a `key` and the color is the `value`.
```python
color_box = {
    "apple": "red",
    "orange": "orange",
    "peach": "pink",
    "banana": "yellow",
}


# looping throgh `keys`
for fruit in color_box:
    print(fruit)

# looping through `values`
for fruit in color_box:
    print(color_box[fruit])

```



I wrote an *article* wite more details about looping through a dictionary.<br>
You can check it out **[HERE](https://nazanin-ashrafi.hashnode.dev/looping-through-dictionaries-in-python)**

