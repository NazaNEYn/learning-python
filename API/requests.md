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

