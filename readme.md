# APIS

### What is an API?
##### API (Application Programming Interface) is a way for two software systems to communicate with each other.
##### An API (Application Programming Interface) is a set of rules and protocols that allows different software applications to communicate with each other. It acts as an intermediary that enables a client to request data or services from a server and receive a response.

#

### What is a REST API?
##### A REST API is a type of API that follows specific rules to communicate over HTTP.
##### REST = Representational State Transfer
##### A REST API is an architectural style for building APIs that uses HTTP methods to perform operations on resources. It follows principles like stateless communication, client-server architecture, and resource-based URLs.
##### Http method (GET, POST, PUT, PATCH, DELETE)
```
GET = Read Data
POST = Create
PUT = Update all
PATCH = Update part
DELETE = Remove
 ```
#### What is Stateless ?
##### Each request is independent. Server does NOT store client state. Every request must contain all required data


#

### What are HTTP status codes? Give examples?
##### HTTP status codes are numbers sent by the server to tell the client what happened with the request.
```
1xx = Information
2xx = Success 
3xx = Redirection
4xx = Client Error
5xx = Server Error 
```

``` 
200(ok)  201(created)  204(no content-> no response body) 
301(Moved Permanently) 302(Found)
400(Bad Request) 401(Unauthorized) 403(Forbidden -> no permission) 404(Not Found)
500(Internal server error) 502(Bad gateway) 503(Service unavailable) 
```

##### Using proper HTTP status codes improves API clarity, helps in debugging, and ensures better communication between frontend and backend systems.

#

### What is JSON and why is it used?
##### JSON is a format used to store and send data.
##### JSON = JavaScript Object Notation
##### JSON (JavaScript Object Notation) is a lightweight, text-based data format used for storing and exchanging data between a client and a server. It is easy for humans to read and write, and easy for machines to parse and generate.

#### Why it is used?
```
1. Easy to Read and write (Human friendly formate)
2. Lightweight (smaller then XML -> fast data transfer) 
3. language Independent
4. Fast Parsing(Easy to convert into objects in code)
5. Standard for Api's (Mostly REST api used JSON)
```
##### JSON is widely used in REST APIs because it is lightweight, faster than XML, and easily supported by JavaScript-based applications like those in the MERN stack.

#


### Difference between query params and path params?
##### Path parameters are used to identify a specific resource in a URL, while query parameters are used to pass optional data such as filters, sorting, or search criteria to the server.

``` 
1. Path Param

GET /api/users/1

app.get('/api/users/:id', (req, res) => {
  const userId = req.params.id;
  res.send(userId);  
}); 

2. Query Param

GET /api/users?age=20&city=Delhi

app.get('/api/users', (req, res) => {
  const { age, city } = req.query;
  res.send({ age, city });
});
```

##### Path parameters should be used for mandatory resource identification, while query parameters are best suited for optional filtering, sorting, and pagination.

#

### What is request and response in HTTP?
##### An HTTP request is a message sent by the client to the server to perform an action, and an HTTP response is the message returned by the server containing the result of that request, including data and status information.
##### Structure of request
```
1. Method (GET, POST, PUT, DELETE)
2. URL 
3. Header
4. Body (optional)
 ```

 ##### An HTTP request is a message sent by the client to the server to perform an action, and an HTTP response is the message returned by the server containing the result of that request, including data and status information.

 #

 ### What is Content-Type header?
 ##### Without Content-Type, server doesn’t know how to read data
 ##### ► Is it JSON? Is it form data? Is it plain text?
 ```
 Comman Content-Type
 1. JSON (Most Common in MERN) => Content-Type: application/json
 2. Form Data => Content-Type: application/x-www-form-urlencoded
 3. File Upload => Content-Type: multipart/form-data
 5. Plain Text => Content-Type: text/plain
  ```
##### In Express applications, middleware like express.json() relies on the Content-Type header to correctly parse incoming request bodies.

#

### What is a URL structure?
##### A URL (Uniform Resource Locator) is the address used to access a resource on the internet.

##### A URL structure defines the format of a web address used to locate resources on a server. It consists of components like protocol, domain, path, and query parameters that help identify and access specific resources.

```
URL Structure
1. Protocol(schema):- http/https
2. Domain(host):- www.example.com (server address)
3. Path (/api/user/1):- Resource location
4. Query Parameters(?age=20):- optional filter
5. Fragement (optional) (Used in frontend navigation (rare in APIs))
```

#

### What is statelessness in REST?
##### The server does NOT remember anything about previous requests.
##### Statelessness in REST means that each client request must contain all the information required to process it, and the server does not store any client-specific state between requests.
```
Statelessness is Important

1. Scalability
    Any server can handle request
    Easy load balancing
2. Simplicity
    No session storage needed
3. Reliability
    If one request fails → others unaffected        
```