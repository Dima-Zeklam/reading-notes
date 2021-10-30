# Spring Security Architecture
Spring Security is a framework that focuses on providing both authentication and authorization to Java applications.

## What is authentication?
![authentication](https://www.cisco.com/c/dam/assets/swa/img/anchor-info/what-is-user-authentication-628x353.png)
Is the process of recognizing a user’s identity(who are you?, that it is actually you accessing the website).
Authentication technology provides access control for systems by checking to see if a user's credentials match the credentials in a database of authorized users or in a data authentication server.
**Example on authentication entering a username and password when you log in to a website.**

### Spring Authentication :

* AuthenticationManager interface :

```
public interface AuthenticationManager {

  Authentication authenticate(Authentication authentication)
    throws AuthenticationException;
}
```
 **AuthenticationManager authenticate returns an Authentication instance with the authenticated flag set to true. Otherwise, if the principal is not valid, it will throw an AuthenticationException. For the last case, it returns null if it can't decide.**

* ProviderManager class:
 The purpose of ProviderManager is to enable you to authenticate users against multiple identity management sources

*  AuthenticationManagerBuilder
Allows for easily building in memory authentication, LDAP authentication, JDBC based authentication, adding UserDetailsService, and adding AuthenticationProvider's.

Example:

```
@Configuration
public class ApplicationSecurity extends WebSecurityConfigurerAdapter {

   ... // web stuff here

  @Autowired
  public void initialize(AuthenticationManagerBuilder builder, DataSource dataSource) {
    builder.jdbcAuthentication().dataSource(dataSource).withUser("dave")
      .password("secret").roles("USER");
  }

}
```
* Interface UserDetailsService
Consist the following method with userDetails type that is Locates the user based on the username.

> UserDetails	loadUserByUsername​(java.lang.String username)	

## Authorization or Access Control
The process of giving someone permission to do or have something.
A good example on authorization is giving someone permission to download a particular file on a server or providing individual users with administrative access to an application .

The core strategy in spring Authorization is `AccessDecisionManager`,There are three implementations provided by the framework and all three delegate to a chain of `AccessDecisionVoter` instances.


## Web Security
In general Web Security refere to protective measures and protocols that organizations adopt to protect the organization from, cyber criminals and threats that use the web channel.

**Spring Security in the web  is based on Servlet Filters**
* A filter is an object that is invoked at the preprocessing and postprocessing of a request. It is mainly used to perform filtering tasks such as conversion, logging, compression, encryption and decryption, input validation.

* Servlet technology is used to create a web application (resides at server side and generates a dynamic web page).Servlet technology is robust and scalable because of java language.
   * Servlet is a class that extends the capabilities of the servers and responds to the incoming requests. It can respond to any requests.
   * Servlet is an interface that must be implemented for creating any Servlet.
   * Servlet is a web component that is deployed on the server to create a dynamic web page.
   * Servlet is an API that provides many interfaces and classes including documentation.


#### FilterChainProxy
FilterChainProxy lets us add a single entry to web. xml and deal entirely with the application context file for managing our web security beans.



