# Response Codes

| Method  | Purpose                                | Common Response Codes |
|---------|----------------------------------------|---------------------|
| GET     | Retrieve data from a server            | 200 OK, 404 Not Found, 401 Unauthorized |
| POST    | Send data to create a resource         | 201 Created, 400 Bad Request, 401 Unauthorized |
| PUT     | Update an existing resource            | 200 OK, 204 No Content, 400 Bad Request |
| PATCH   | Partially update a resource            | 200 OK, 204 No Content, 400 Bad Request |
| DELETE  | Remove a resource                      | 200 OK, 204 No Content, 404 Not Found |
| HEAD    | Retrieve only headers of a resource    | 200 OK, 404 Not Found |
| OPTIONS | Get supported HTTP methods or options  | 200 OK |

