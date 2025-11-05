# How to create a `DataFrame`:

```python
data = pd.DataFrame([[1, 2, 3], [4, 5, 6], [7, 8, 9]], columns=["A", "B", "C"])
```

## Get the rows:
`head()`

```python
data = pd.DataFrame([[1, 2, 3], [4, 5, 6], [7, 8, 9]], columns=["A", "B", "C"])
print(data.head())

#    A  B  C
# 0  1  2  3
# 1  4  5  6
# 2  7  8  9
```

You can specify the number of the rows:
`head(2)`, `head(5)` etc

## Get the bottom rows:
`data.tail()`

```python
data = pd.DataFrame([[1, 2, 3], [4, 5, 6], [7, 8, 9]], columns=["A", "B", "C"])
print(data.tail(1))

#    A  B  C
# 2  7  8  9
```

## Getting the header:
`columns`

```python
data = pd.DataFrame([[1, 2, 3], [4, 5, 6], [7, 8, 9]], columns=["A", "B", "C"])
print(data.columns)

# Index(['A', 'B', 'C'], dtype='object')
```

# Specifying the `index`:

```python
data = pd.DataFrame(
    [[1, 2, 3], [4, 5, 6], [7, 8, 9]], columns=["A", "B", "C"], index=["x", "y", "z"]
)
print(data)

#    A  B  C
# x  1  2  3
# y  4  5  6
# z  7  8  9
```

```python
data = pd.DataFrame(
    [[1, 2, 3], [4, 5, 6], [7, 8, 9]], columns=["A", "B", "C"], index=["x", "y", "z"]
)
print(data.index)

# Index(['x', 'y', 'z'], dtype='object')
```

------------------------------------------------------------------------

# How to open a csv file:
```python
data = pandas.read_csv("weather_data.csv")
print(data)
```

```md
day,temp,condition
Monday,12,Sunny
Tuesday,14,Rain
Wednesday,15,Rain
Thursday,14,Cloudy
Friday,21,Sunny
Saturday,22,Sunny
Sunday,24,Sunny
```

<hr>

# Basic data structures in pandas

![Gemini_Generated_Image_43y35h43y35h43y3](https://github.com/user-attachments/assets/06d8560b-16a5-4a23-aa7e-0683238e2cfd)


<hr>


# How to get a column:

There are two ways: <br>

**1:**

```python
data = pandas.read_csv("weather_data.csv")
print(data["temp"])


# 0    12
# 1    14
# 2    15
# 3    14
# 4    21
# 5    22
# 6    24
```

**2:**

```python
data = pandas.read_csv("weather_data.csv")
print(data.temp)
```


**So**
```python
data["tempt"] # --> it's almost like you're treating it as a dict and you pul out each column by a `key`
data.tempt    # --> it's almost like you're treating like an `object.`
```

<hr>


# How to check the type:

```python
data = pandas.read_csv("weather_data.csv")
print(type(data))

# <class 'pandas.core.series.Series'>
```

```python
data = pandas.read_csv("weather_data.csv")
print(type(data))

# <class 'pandas.core.frame.DataFram*'>
```

<hr>



# Converting DataFrame to a dictionary:
`DataFrame.to_dict()`

```python
data = pandas.read_csv("weather_data.csv")
to_dict = data.to_dict()
print(to_dict)


# {
#     "day": {
#         0: "Monday",
#         1: "Tuesday",
#         2: "Wednesday",
#         3: "Thursday",
#         4: "Friday",
#         5: "Saturday",
#         6: "Sunday",
#     },
#     "temp": {0: 12, 1: 14, 2: 15, 3: 14, 4: 21, 5: 22, 6: 24},
#     "condition": {
#         0: "Sunny",
#         1: "Rain",
#         2: "Rain",
#         3: "Cloudy",
#         4: "Sunny",
#         5: "Sunny",
#         6: "Sunny",
#     },
# }
```

<hr>


# Converting Series to list:
`Series.to_list()`

```python
data = pandas.read_csv("weather_data.csv")
to_list = data["temp"].to_list()
print(to_list)

# [12, 14, 15, 14, 21, 22, 24]
```

<hr>

| Statistical Term | Calculation / Meaning | When to Use It |
| :--- | :--- | :--- |
| **Mean (Average)** | Sum of all values divided by the count. | When data is evenly distributed and you need a precise average. |
| **Median (Middle Value)** | The middle value after ordering the data. | When data has **outliers** (extreme values) that would skew the mean. |
| **Mode (Most Frequent)** | The value that appears most often in the data set. | When you want to know the most common item or category. |


# How to get the average:
`Series.mean()`

```python
data = pandas.read_csv("weather_data.csv")
print(data["temp"].mean())
# 17.428571428571427
```

<hr>

# How to get a row:

First get a hold of the entired data table:
`data[]`

Then, inside the data table, get hold of the column that we want to search through:
`data[data.day]`

Then inside that column we can get the row we want:
`data[data.day == "Monday"]`

```python
print(data[data.day == "Monday"])
# 0  Monday    12     Sunny
```


<hr>

# Create a DataFrame from scratch:

```python
data = {
    "name": "Pilk",
    "formula": ["Pepsi", "Milk"],
}

print(pandas.DataFrame([data]))

#    name        formula
# 0  Pilk  [Pepsi, Milk]
```


```python
data = {
    "name": ["Amy", "Ashley"],
    "age": ["32", "35"],
}

print(pandas.DataFrame(data))

#      name age
# 0     Amy  32
# 1  Ashley  35
```

<hr>

# Converting to a `csv` file:

```python
data = {
    "name": ["Amy", "Ashley"],
    "age": ["32", "35"],
}

data = pandas.DataFrame(data)
data.to_csv("data.csv")
```

<hr>

