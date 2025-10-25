# How to open a csv file:
```python
data = pandas.read_csv("weather_data.csv")
print(data)
```


# Basic data structures in pandas

![Gemini_Generated_Image_43y35h43y35h43y3](https://github.com/user-attachments/assets/06d8560b-16a5-4a23-aa7e-0683238e2cfd)

<hr>
# How to check the type:
```python
data = pandas.read_csv("weather_data.csv")
print(type(data))
```




| Statistical Term | Calculation / Meaning | When to Use It |
| :--- | :--- | :--- |
| **Mean (Average)** | Sum of all values divided by the count. | When data is evenly distributed and you need a precise average. |
| **Median (Middle Value)** | The middle value after ordering the data. | When data has **outliers** (extreme values) that would skew the mean. |
| **Mode (Most Frequent)** | The value that appears most often in the data set. | When you want to know the most common item or category. |
