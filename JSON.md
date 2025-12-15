| Method | Direction (Conversion) | Target/Source | Purpose (Use Case) | Analogy |
| :--- | :--- | :--- | :--- | :--- |
| `json.dumps()` | Python $\rightarrow$ JSON (Encode/Serialize) | String | To convert a **Python object** (like a dict) into a single **JSON-formatted string**, typically for sending over a network. | Placing your data into a sealed shipping box ready for transit. |
| `json.load()` | JSON $\rightarrow$ Python (Decode/Deserialize) | File | To convert data read from a **JSON file** into a **Python object** (like a dict) so you can use it in your program. | Receiving a shipping box (the file) and opening it to access the data inside. |
| `json.dump()` | Python $\rightarrow$ JSON (Encode/Serialize) | File | To convert a **Python object** (like a dict) and write it directly into an open **file** in JSON format for storage. | Writing your data down neatly onto a permanent ledger (the file). |
| `json.loads()` | JSON $\rightarrow$ Python (Decode/Deserialize) | String | To convert a **JSON-formatted string** you received (e.g., from an API response) back into a **Python object**. | Taking a sealed shipping box (the string) and immediately opening it to access the data. |


-------

| Step/Method | Primary Action | Python Method / Concept | Data Flow | Explanation |
| :--- | :--- | :--- | :--- | :--- |
| 1. Reading Data | Load the JSON file data into a Python dictionary. | `json.load(file_object)` | File $\rightarrow$ Python dict | Reads the entire JSON file content and converts it into a Python object (usually a dictionary or list) so you can work with it. |
| 2. Modifying Data | Update the data in the Python dictionary. | `dictionary.update(...)` | Python dict $\leftrightarrow$ Python dict | This is a standard Python dictionary method used to add new key-value pairs or change existing ones after you've loaded the data. |
| 3. Writing Data | Dump the modified Python dictionary back into the JSON file. | `json.dump(data, file_object)` | Python dict $\rightarrow$ File | Takes your updated Python dictionary and writes it to the open file, converting it back into the JSON text format. |


-----

## Examples

* **Save a single dictionary to JSON**

```python
import json

movie = {
    "title": "Inception",
    "year": 2010,
    "rating": "PG-13",
    "gross": "$829,895,144"
}

# Save to JSON file
with open("movie.json", "w") as f:
    json.dump(movie, f, indent=4)

print("Saved single movie to movie.json")
```
```json
{
    "title": "Inception",
    "year": 2010,
    "rating": "PG-13",
    "gross": "$829,895,144"
}
```

* **Save a list of dictionaries to JSON**

```python
import json

movies = [
    {"title": "Inception", "year": 2010, "rating": "PG-13", "gross": "$829,895,144"},
    {"title": "Avatar", "year": 2009, "rating": "PG-13", "gross": "$2,923,706,026"},
    {"title": "Titanic", "year": 1997, "rating": "PG-13", "gross": "$2,257,844,554"}
]

# Save to JSON file
with open("movies.json", "w") as f:
    json.dump(movies, f, indent=4)

print("Saved list of movies to movies.json")
```

```json
[
    {
        "title": "Inception",
        "year": 2010,
        "rating": "PG-13",
        "gross": "$829,895,144"
    },
    {
        "title": "Avatar",
        "year": 2009,
        "rating": "PG-13",
        "gross": "$2,923,706,026"
    },
    {
        "title": "Titanic",
        "year": 1997,
        "rating": "PG-13",
        "gross": "$2,257,844,554"
    }
]
```


* **Reading the JSON back into Python**

```python
import json

# Load movies from JSON
with open("movies.json", "r") as f:
    movies = json.load(f)

for movie in movies:
    print(f"{movie['title']} ({movie['year']}) → {movie['gross']}")
```

```json
Inception (2010) → $829,895,144
Avatar (2009) → $2,923,706,026
Titanic (1997) → $2,257,844,554
```

* **Update JSON File**

`movies.json`
```json
[
    {
        "title": "movie_01",
        "year": 1993,
        "rating": 5.6,
        "gross": "5.439.247"
    },
    {
        "title": "movie_02",
        "year": 1793,
        "rating": 1.6,
        "gross": "4.222.247"
    },
    {
        "title": "movie_03",
        "year": 2020,
        "rating": 3.6,
        "gross": "1.419.888"
    }
]
```


```python
import json

# Step 1: Load the existing movies from `movies.json`
with open("movies.json") as file:
    movies = json.load(file)

# Step 2: Create a new movie dictionary
new_movie = {
    "title": "movie_04",
    "year": 2025,
    "rating": 7.8,
    "gross": "6.500.000",
}

# Step 3: Add the new movie to the list
movies.append(new_movie)

# Step 5: Save the updated list back to `movies.json`
with open("movies.json", "w") as file:
    json.dump(movies, file, indent=4)

# Step 6: Print all movie titles to verify
for movie in movies:
    print(movie["title"])
```

The updated `movie.json` file:

```json
[
    {
        "title": "movie_01",
        "year": 1993,
        "rating": 5.6,
        "gross": "5.439.247"
    },
    {
        "title": "movie_02",
        "year": 1793,
        "rating": 1.6,
        "gross": "4.222.247"
    },
    {
        "title": "movie_03",
        "year": 2020,
        "rating": 3.6,
        "gross": "1.419.888"
    },
    {
        "title": "movie_04",
        "year": 2025,
        "rating": 7.8,
        "gross": "6.500.000"
    }
]
```
