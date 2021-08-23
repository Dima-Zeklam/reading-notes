# CRUD

![CRUD](https://www.dorusomcutean.com/wp-content/uploads/2020/03/crud.jpg)

### In your own words, describe what each group of status code represents:

**100’s =** informational status codes,tell the client that the header part of the request has been received and the server will try to comply with a transmission demand of the client.

**200’s =** success codes, tell the client that its request was accepted.but this doesn’t mean the request was successfully processed only that it met all validation requirements at the time of sending.

**300’s =** redirection codes, tell the client that the resource they are requesting isn’t available at the expected location anymore. 

**400’s =** error codes, a client is sending incorrect input and should confirm the input parameters are correct before retrying the request.

**500’s =**  server error codes, indicate problems with overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server.

### What is a status code 202?
Accepted - Often used for asynchronous processing. This code tells the client that the request was valid, but its processing will finish sometime in the future. 

### What is a status code 308?
 Permanent Redirect - This tells the client to use another URL to access the resource and not use the current URL anymore. It’s helpful when we have multiple endpoints for one resource, but don’t want to implement reading from all of them.

### What code would you use if an update didn’t return data to a client?
204 No Content - A proper code for updates that don’t return data to the client.

### What code would you use if a resource used to exist but no longer does?
410 Gone
### What is the ‘Forbidden’ status code?
403 Forbidden - The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.

### Why do we need to pull our MongoDB database string out of our server and put it into our .env?
because when we gonna deploy the work will not use the localhost 
### What is middleware?
 is a type of computer software that provides services to software applications beyond those available from the operating system.
### What does app.use(express.json()) do?
alows to use any middleware thats you want .
### What does the /:id mean in a route?
allow us  access to whatever they pass in after the first slash. 
### What is the difference beween PUT and PATCH?
The main difference between the PUT and PATCH method is that the PUT method uses the request URI to supply a modified version of the requested resource which replaces the original version of the resource, whereas the PATCH method supplies a set of instructions to modify the resource.
### How do you make a defalut value in a schema?

```
const subscruibedSchema = new mongoose.Schema({
    name:{

    },
    subscribe:{

    }
});
```

### What does a 500 error status code mean?
indicates that the server encountered an unexpected condition that prevented it from fulfilling the request.
### What is the difference between a status 200 and a status 201?
200 - OK,status code is by far the most common returned. It means, simply, that the request was received and understood and is being processed.
but 201 - Created, status code indicates that a request was successful and as a result, a resource has been created (for example a new page).

## Things I want to know more about
* Another mangoose methods.