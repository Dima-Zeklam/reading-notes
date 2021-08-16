# REST

### Who is Roy Fielding?
**Roy Thomas Fielding** (born 1965) is an American computer scientist, one of the principal authors of the HTTP specification and the originator of the Representational State Transfer (REST) architectural style. He is an authority on computer network architecture and co-founded the Apache HTTP Server project.

### Why don’t the techniques that we use today work well when we need to be able to talk to all of the machines in the world?
When Fielding and his colleagues started building the web, being able to talk to any machine anywhere in the world was a primary concern. But most of the techniques developers later used to get computers to talk to each other didn't have those requirements. You just needed to talk to a small group of machines.
### What is the HTTP protocol that Fielding and his friends created?

![HTTP](https://static6.depositphotos.com/1043957/580/i/600/depositphotos_5805232-stock-photo-world-connection.jpg)

 HTTP—this protocol Fielding and his friends created—is all about applying verbs to nouns. For instance, when you go to a web page, the browser does an HTTP GET on the URL you typed in and back comes a web page.

### What does a `GET` do?

**GET** is used to request data from a specified resource. **GET** is one of the most common.HTTP methods.
![HTTP](https://res.cloudinary.com/practicaldev/image/fetch/s--9G_NLci7--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1uapyaa2ob49xctta1j7.png)

### What does a `POST` do?
**POST** is used to send data to a server to create/update a resource.**POST** is one of the most common HTTP methods.Also:
* POST requests are never cached
* POST requests do not remain in the browser history
* POST requests cannot be bookmarked
* POST requests have no restrictions on data length


### What does `PUT` do?
**PUT** is used to send data to a server to create/update a resource.

### What does `PATCH` do?
**HEAD** is almost identical to GET, but without the response body.
In other words, if GET /users returns a list of users, then HEAD /users will make the same request but will not return the list of users.

### Did you get your API key?
 Yes

## Things I want to know more about
* More about REST representational state transfer
