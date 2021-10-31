# Spring Boot and OAuth2

## The OAuth 2.0 Authorization Framework
The OAuth 2.0 authorization framework is a protocol that allows a user to grant a third-party web site or application access to the user's protected resources, without necessarily revealing their long-term credentials or even their identity.

![OAuth 2.0](https://miro.medium.com/max/935/1*MR3NxY-jCGa9t7KShExnYg.png)
#### An OAuth 2.0 flow has the following roles:

1. Resource Owner: Entity that can grant access to a protected resource. Typically, this is the end-user.

2. Resource Server: Server hosting the protected resources. This is the API you want to access.

3. Client: Application requesting access to a protected resource on behalf of the Resource Owner.

4. Authorization Server: Server that authenticates the Resource Owner and issues access tokens after getting proper authorization. 

## Single Sign On With GitHub
* Creating a New Project

Do this on the command line:
```
$ mkdir ui && cd ui
$ curl https://start.spring.io/starter.tgz -d style=web -d name=simple | tar -xzvf -
```

* Add a Home Page
create index.html in the src/main/resources/static folder, the index.html contains the following :

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="utf-8"/>
    <meta http-equiv="X-UA-Compatible" content="IE=edge"/>
    <title>Demo</title>
    <meta name="description" content=""/>
    <meta name="viewport" content="width=device-width"/>
    <base href="/"/>
    <link rel="stylesheet" type="text/css" href="/webjars/bootstrap/css/bootstrap.min.css"/>
    <script type="text/javascript" src="/webjars/jquery/jquery.min.js"></script>
    <script type="text/javascript" src="/webjars/bootstrap/js/bootstrap.min.js"></script>
</head>
<body>
	<h1>Demo</h1>
	<div class="container"></div>
</body>
</html>
```
**you need to add pom.xml as well by adding jQuery and Twitter Bootstrap:**

```
<dependency>
	<groupId>org.webjars</groupId>
	<artifactId>jquery</artifactId>
	<version>3.4.1</version>
</dependency>
<dependency>
	<groupId>org.webjars</groupId>
	<artifactId>bootstrap</artifactId>
	<version>4.3.1</version>
</dependency>
<dependency>
	<groupId>org.webjars</groupId>
	<artifactId>webjars-locator-core</artifactId>
</dependency>
```

* add Spring Security as a dependency

```
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-oauth2-client</artifactId>
</dependency>
```

* you need to configure your app to use GitHub as the authentication provider by [addAdd a New GitHub app](https://spring.io/guides/tutorials/spring-boot-oauth2/#github-register-application), [Configure application.yml](https://spring.io/guides/tutorials/spring-boot-oauth2/#github-application-config) and [Boot up the application](https://spring.io/guides/tutorials/spring-boot-oauth2/#github-boot-application).

* Create the endpoints.
* Adding the Client Registration.
* Add users Database.
* Adding an Error Message, you can configure an `AuthenticationFailureHandler` :

```
protected void configure(HttpSecurity http) throws Exception {
	// @formatter:off
	http
	    // ... existing configuration
	    .oauth2Login(o -> o
            .failureHandler((request, response, exception) -> {
			    request.getSession().setAttribute("error.message", exception.getMessage());
			    handler.onAuthenticationFailure(request, response, exception);
            })
        );
}
```


