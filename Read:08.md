# APIs 

### 1. What does REST stand for?
![REST](https://miro.medium.com/max/616/1*PNuFFadttQrMTAdFDX8XSg.png)
**REST** stand for *Representational State Transfer*  is an architectural style for building distributed systems based on hypermedia. REST is independent of any underlying protocol and is not necessarily tied to HTTP. However, most common REST API implementations use HTTP as the application protocol, and this guide focuses on designing REST APIs for HTTP.

### 2. REST APIs are designed around a *resources*

### 3. What is an identifer of a resource? Give an example.
A URI contains scheme, authority, path, query, and a fragment. Some most common URI schemes are HTTP, HTTPs, ftp, Idap, telnet.
### 4. What are the most common HTTP verbs?
The primary or most-commonly-used HTTP verbs (or methods, as they are properly called) are POST, GET, PUT, PATCH, and DELETE. 
### 5. What should the URIs be based on?
The purpose of URIs is to uniquely and reliably name resources on the Web.
### 6. Give an example of a good URI.

> http://domain.com/posts/servers/nginx-ubuntu-10.04

### 7. What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?
try to avoid "chatty" web APIs that expose a large number of small resources. Such an API may require a client application to send multiple requests to find all of the data that it requires. Instead, you might want to denormalize the data and combine related information into bigger resources that can be retrieved with a single request. However, you need to balance this approach against the overhead of fetching data that the client doesn't need. 

### 8. What status code does a successful GET request return?
A successful GET method typically returns HTTP status code 200 (OK).

### 9. What status code does an unsuccessful GET request return?
If the resource cannot be found, the method should return 404 (Not Found).

### 10. What status code does a successful POST request return?
* If a POST method creates a new resource, it returns HTTP status code 201 (Created).
* If the method does some processing but does not create a new resource, the method can return HTTP status code 200 and include the result of the operation in the response body.
### 11. What status code does a successful DELETE request return?
If the delete operation is successful, the web server should respond with HTTP status code 204 (No Content)