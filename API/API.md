# what is API?
An API (Application Programming Interface) is basically a bridge that lets your program or app access data or functionality from another service, website, or company, without having to recreate it yourself.


# API endpoint
An API endpoint is a specific URL. <br>
Example: `https://api.example.com`

# API request
An API request is like telling the bank teller exactly what you want them to do, and the teller (endpoint) responds with the result

---------------------

```python
response = requests.get("http://api.open-notify.org/iss-now.json")

print(response)
# <Response [200]>

print(response.status_code)
# 200
```
