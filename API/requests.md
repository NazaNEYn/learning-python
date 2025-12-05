# Python Requests Library 



## Installation

### Using pip:
```bash
pip install requests
```

### Using uv:
If you have `uv` installed:
```bash
uv pip install requests
```

---

## Importing Requests
```python
import requests
```

---

## HTTP Methods


| Method  | Purpose                                |
|---------|----------------------------------------|
| GET     | Retrieve data from a server            |
| POST    | Send data to create a resource         |
| PUT     | Update an existing resource            |
| PATCH   | Partially update a resource            |
| DELETE  | Remove a resource                      |
| HEAD    | Retrieve only headers of a resource    |
| OPTIONS | Get supported HTTP methods or options  |


----

## 1. GET
**Purpose:** Retrieve data from a server.

```python
import requests

response = requests.get('https://api.example.com/data', params={'id': 123})
print(response.status_code)
print(response.json())
```

**Key Parameters:**
- `params` → Dictionary of URL query parameters.
- `headers` → HTTP headers to send.
- `timeout` → Maximum wait time for a response.

---

## 2. POST
**Purpose:** Send data to a server to create a resource.

```python
payload = {'name': 'Alice', 'age': 25}
response = requests.post('https://api.example.com/users', json=payload)
print(response.status_code)
print(response.json())
```

**Key Parameters:**
- `data` → Form-encoded data.
- `json` → JSON payload.
- `headers` → HTTP headers.
- `timeout` → Maximum wait time for a response.

---

## 3. PUT
**Purpose:** Update an existing resource on the server.

```python
payload = {'age': 26}
response = requests.put('https://api.example.com/users/1', json=payload)
print(response.status_code)
print(response.json())
```

**Key Parameters:** Same as `POST`.

---

## 4. PATCH
**Purpose:** Partially update a resource (only specific fields).

```python
payload = {'age': 27}
response = requests.patch('https://api.example.com/users/1', json=payload)
print(response.status_code)
print(response.json())
```

**Key Parameters:** Same as `POST`.

---

## 5. DELETE
**Purpose:** Remove a resource from the server.

```python
response = requests.delete('https://api.example.com/users/1')
print(response.status_code)
```

**Key Parameters:**
- `headers` → HTTP headers.
- `timeout` → Maximum wait time.

---

## 6. HEAD
**Purpose:** Retrieve only headers from a resource, without the body.

```python
response = requests.head('https://api.example.com/data')
print(response.headers)
print(response.status_code)
```

---

## 7. OPTIONS
**Purpose:** Get supported HTTP methods or server options for a URL.

```python
response = requests.options('https://api.example.com/data')
print(response.headers)
print(response.status_code)
```

---

## 8. Other Notes
- All methods can use **`headers`**, **`auth`**, **`timeout`**, **`cookies`**, and **`params`** where applicable.
- Use `response.raise_for_status()` to automatically raise an exception for HTTP errors.
- Use `response.json()` to parse JSON responses.

---

## Summary
The `requests` library supports all common HTTP methods (`GET`, `POST`, `PUT`, `PATCH`, `DELETE`, `HEAD`, `OPTIONS`) making it easy to interact with APIs in Python. Choosing the right method depends on the action you want to perform on the server.




---

## Making Requests

### GET Request
Retrieve data from a specified resource.
```python
response = requests.get('https://api.example.com/data')
print(response.status_code)
data = response.json()
print(data)
```

### POST Request
Send data to a server.
```python
payload = {'name': 'Alice', 'age': 25}
response = requests.post('https://api.example.com/users', json=payload)
print(response.status_code)
print(response.json())
```

### PUT Request
Update existing data on the server.
```python
payload = {'age': 26}
response = requests.put('https://api.example.com/users/1', json=payload)
print(response.status_code)
```

### DELETE Request
Delete a resource.
```python
response = requests.delete('https://api.example.com/users/1')
print(response.status_code)
```

---

## Common Parameters
- **headers**: Dictionary of HTTP headers to send with the request.
- **params**: Dictionary of URL query parameters.
- **json**: JSON data to send in POST/PUT requests.
- **timeout**: Number of seconds to wait for a response.
- **auth**: Tuple for authentication `(username, password)`.

Example with headers and params:
```python
headers = {'Authorization': 'Bearer YOUR_TOKEN'}
params = {'limit': 10, 'sort': 'desc'}
response = requests.get('https://api.example.com/items', headers=headers, params=params)
print(response.json())
```

---

## Handling Responses
```python
# Status code
print(response.status_code)

# Text content
print(response.text)

# JSON content
data = response.json()
print(data)

# Headers
print(response.headers)
```

---

## Error Handling

`response.raise_for_status()`:<br>

* It’s a built-in method of the response object.
* It checks the HTTP response code of your request.
* If the response indicates an error (status codes 4xx or 5xx), it raises an exception.
* If the response is successful (2xx) or a redirect (3xx), it does nothing.



![ChatGPT Image Dec 5, 2025, 04_04_34 PM](https://github.com/user-attachments/assets/a330bec0-14a4-4f74-926d-6047ada0e038)


```python
import requests

response = requests.get("https://api.example.com/data")

# Raise an error if the request failed
response.raise_for_status()

# If no error, continue
data = response.json()
print(data)
```


```python
try:
    response = requests.get('https://api.example.com/data', timeout=5)
    response.raise_for_status()  # Raises HTTPError for bad responses (4xx or 5xx)
    data = response.json()
except requests.exceptions.HTTPError as errh:
    print('HTTP Error:', errh)
except requests.exceptions.ConnectionError as errc:
    print('Connection Error:', errc)
except requests.exceptions.Timeout as errt:
    print('Timeout Error:', errt)
except requests.exceptions.RequestException as err:
    print('Something went wrong:', err)
```

---

## Sessions
Use `Session` to persist parameters, cookies, or headers across multiple requests.
```python
session = requests.Session()
session.headers.update({'Authorization': 'Bearer YOUR_TOKEN'})
response = session.get('https://api.example.com/data')
print(response.json())
```

---

