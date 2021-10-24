# Spring

![Spring Framework ](https://i1.wp.com/readlearncode.com/wp-content/uploads/2016/02/kenhlaptrinh-java-spring-logo.png?fit=851%2C446&ssl=1)


Spring Framework is a Java platform that provides comprehensive infrastructure support for developing Java applications. The framework also can be defined as a structure where we find solution of the various technical problems.

#### Advantages of Spring Framework:
1. Predefined Templates

2. Loose Coupling because of dependency injection.
3. Easy to test - The Dependency Injection makes easier to test the application, Spring framework doesn't require server.
4. Lightweight - The Spring Framework doesn't force the programmer to inherit any class or implement any interface. 

5. Fast Development
6. Powerful abstraction
It provides powerful abstraction to JavaEE specifications such as JMS, JDBC, JPA and JTA.
7. Declarative support - It provides declarative support for caching, validation, transactions and formatting.

### Dependency Injection and Inversion of Control
Java applications consist of objects that collaborate to form the application proper. Thus the objects in an application have dependencies on each other.
**Inversion of Control (IoC)** component addresses this concern by providing a formalized means of composing disparate components into a fully working application ready for use.

### Modules
The Spring Framework consists of features organized into about 20 modules. These modules are grouped into Core Container, Data Access/Integration, Web, AOP (Aspect Oriented Programming), Instrumentation, and Test.

![Modules](https://docs.spring.io/spring-framework/docs/3.0.0.M3/reference/html/images/spring-overview.png)


### Create a Web Controller
Example:
```
package com.example.servingwebcontent;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RequestParam;

@Controller
public class GreetingController {
   // The @GetMapping annotation ensures that HTTP GET requests to /greeting are mapped to the greeting() method.
	@GetMapping("/greeting")
    @RequestParam binds the value of the query string parameter
	public String greeting(@RequestParam(name="name", required=false, defaultValue="World") String name, Model model) {
		model.addAttribute("name", name);
		return "greeting";
	}

}
```

### Spring Boot Devtools
Spring Boot is a project that is built on the top of the Spring Framework. It provides an easier and faster way to set up, configure, and run both simple and web-based applications.
*  Spring Boot is the combination of Spring Framework and Embedded Servers.
![Spring Boot](https://miro.medium.com/max/866/1*fF7pymj3MgkhV_8uMFShlA.png)

* The dependency injection approach is used in Spring Boot.
* It contains powerful database transaction management capabilities.
* It reduces the cost and development time of the application.


### Spring MVC (Model-View-Controller)
A Spring MVC is a Java framework which is used to build web applications. It implements all the basic features of a core spring framework like Inversion of Control, Dependency Injection.

### Thymeleaf
The Thymeleaf is an open-source Java library. It is a HTML5/XHTML/XML template engine. It is a server-side Java template engine for both web (servlet-based) and non-web (offline) environments. It provides full integration with Spring Framework.

#### Request parameters
Request parameters can be easily accessed in Thymeleaf views. Request parameters are passed from the client to server like:

>  https://example.com/query?q=Thymeleaf+Is+Great!

```
    @Controller //sends a redirect with a request parameter
        public class SomeController {
            @RequestMapping("/")
            public String redirect() {
                return "redirect:/query?q=Thymeleaf+Is+Great!";
            }
        }
```

### Spring beans
a Spring bean is an object that form the backbone of your application and that is managed by the Spring IoC container.

Example: 

```
 //@urlService refers to a Spring Bean registered at your context
    @Configuration
        public class MyConfiguration {
            @Bean(name = "urlService")
            public UrlService urlService() {
                return () -> "domain.com/myapp";
            }
        }

        public interface UrlService {
            String getApplicationUrl();
        }
```