# Spring RESTful Routing & Static Files


### Spring RequestMapping
**@RequestMapping** is the most common and widely used annotation in Spring MVC. It is used to map web requests onto specific handler classes and/or handler methods.

* It has the following optional options

  * name: Assign a name to this mapping.
  * value:  The primary mapping expressed by this annotation.
  * method: The HTTP request methods to map to
  * headers: The headers of the mapped request, narrowing the primary mapping.


**Some Examples:**

1. @RequestMapping — by Path

```
@RequestMapping(value = "/ex/foos", method = RequestMethod.GET)
@ResponseBody
public String getFoosBySimplePath() {
    return "Get some Foos";
}
```

2. @RequestMapping — the HTTP Method

Sometimes we want to perform different operations based on the HTTP method used, even though request URI remains same. We can use @RequestMapping method variable to narrow down the HTTP methods for which this method will be invoked.

```
@RequestMapping(value = "/ex/foos", method = POST)
@ResponseBody
public String postFoos() {
    return "Post some Foos";
}
```

3. RequestMapping and HTTP Headers

```
@RequestMapping(value = "/ex/foos", headers = "key=val", method = GET)
@ResponseBody
public String getFoosWithHeader() {
    return "Get some Foos with Header";
}
```

4. @RequestMapping with Produces and Consumes: 
**@RequestMapping provides produces and consumes variables where we can specify the request content-type for which method will be invoked and the response content type. For example:**

```
@RequestMapping(value="/method6", produces={"application/json","application/xml"}, consumes="text/html")
@ResponseBody
public String method6(){
	return "method6";
}
```

5. @RequestMapping with @PathVariable: 
 @PathVariable annotation which we can map the URI variable to one of the method arguments. For example:

 ```
 @RequestMapping(value="/method7/{id}")
@ResponseBody
public String method7(@PathVariable("id") int id){
	return "method7 with id="+id;
}
 ```


### REST API with Spring
![REST API with Spring](https://miro.medium.com/max/1024/1*45Y1dRGskA0-memvDBd6Hg.png)

**REST APIs** are one of the most common kinds of web services available today. They allow various clients including browser apps to communicate with a server via the REST API.
It is not a protocol or standard. While REST APIs can be accessed through a number of communication protocols, most commonly, they are called over HTTPS.

* The most common methods include GET, POST, PUT, and DELETE.

 * GET retrieves resources.
 * POST submits new data to the server.
 * PUT updates existing data.
 * DELETE removes data.

#### What makes a good REST API?

1. They need accuracy and performance, to keep up with the demands of the client processes that depend on them.
2. need to be documented and designed well enough that programmers can usefully develop reliable applications with them.
3. support X-HTTP-METHOD-Override to accommodate picky proxies
4. use HTTP verbs as Fielding originally defined
5. express URLs with nouns rather than verbs
6. track version and make expressive use of HTTP Status Codes
7. explicitly design in other commercially-significant API-specific features
8. log activity and limit rates
9. handle errors carefully and explicitly


### CrudRepository, JpaRepository, and PagingAndSortingRepository in Spring Data

#### Spring Data
Spring Data is Spring-based programming model for data access. It reduces the amount of code needed for working with databases and datastores. It consists of several modules. 

#### CrudRepository 
Is a Spring Data interface for generic CRUD operations on a repository of a specific type, It provide following methods:

* save(…) – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch
* findOne(…) – get a single entity based on passed primary key value
* findAll() – get an Iterable of all available entities in database
* count() – return the count of total entities in a table
* delete(…) – delete an entity based on the passed object
* exists(…) – verify if an entity exists based on the passed primary key value
 
#### JpaRepository 
Is JPA specific extension of Repository . It contains the full API of CrudRepository and PagingAndSortingRepository, It provide following methods:

* findAll() – get a List of all available entities in database
* findAll(…) – get a List of all available entities and sort them using the provided condition
* save(…) – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch
* flush() – flush all pending task to the database
* saveAndFlush(…) – save the entity and flush changes immediately
* deleteInBatch(…) – delete an Iterable of entities.

#### PagingAndSortingRepository 
Is an extension of CrudRepository to provide additional methods to retrieve entities using the pagination and sorting abstraction. It provides two methods :
* Page findAll(Pageable pageable) – returns a Page of entities meeting the paging restriction provided in the Pageable object.
* Iterable findAll(Sort sort) – returns all entities sorted by the given options. No paging is applied here.












