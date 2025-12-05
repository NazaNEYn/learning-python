# HTTP Status Code Categories

| Code Range | Meaning                  |
|------------|-------------------------|
| 1xx        | Informational (request received, continuing) |
| 2xx        | Success (request succeeded) |
| 3xx        | Redirection (follow a new URL) |
| 4xx        | Client Error (bad request, unauthorized, not found) |
| 5xx        | Server Error (server failed to handle request) |


# Common Response Codes

| Method  | Purpose                                | Common Response Codes |
|---------|----------------------------------------|---------------------|
| GET     | Retrieve data from a server            | 100 Continue, 200 OK, 301 Moved Permanently, 302 Found, 304 Not Modified, 401 Unauthorized, 404 Not Found |
| POST    | Send data to create a resource         | 100 Continue, 200 OK, 201 Created, 400 Bad Request, 401 Unauthorized |
| PUT     | Update an existing resource            | 100 Continue, 200 OK, 204 No Content, 400 Bad Request |
| PATCH   | Partially update a resource            | 100 Continue, 200 OK, 204 No Content, 400 Bad Request |
| DELETE  | Remove a resource                      | 100 Continue, 200 OK, 204 No Content, 404 Not Found |
| HEAD    | Retrieve only headers of a resource    | 100 Continue, 200 OK, 301 Moved Permanently, 302 Found, 404 Not Found |
| OPTIONS | Get supported HTTP methods or options  | 100 Continue, 200 OK |

