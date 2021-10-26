# Related Resources and Integration Testing

## The relationships between entities in Spring Data REST
1. One-to-One Relationship

using the **@OneToOne** annotation.

* The Data Model
Example : 
Here we create relationship between Library and address which us one to one. **We must be careful to have different names for each association resource**

```
@Entity
public class Library {

    @Id
    @GeneratedValue
    private long id;

    @Column
    private String name;

    @OneToOne
    @JoinColumn(name = "address_id")
    @RestResource(path = "libraryAddress", rel="address")
    private Address address;
    
    // standard constructor, getters, setters
}

@Entity
public class Address {

    @Id
    @GeneratedValue
    private long id;

    @Column(nullable = false)
    private String location;

    @OneToOne(mappedBy = "address")
    private Library library;

    // standard constructor, getters, setters
}
```
* The Repositories
Example to one to one Relationship between interfaces:

```
public interface LibraryRepository extends CrudRepository<Library, Long> {}
public interface AddressRepository extends CrudRepository<Address, Long> {}
``` 

2.  One-to-Many Relationship

using the **@OneToMany** annotation.
* The Data Model
example on One-to-Many Relationship between book and library 

```
@Entity
public class Book {

    @Id
    @GeneratedValue
    private long id;
    
    @Column(nullable=false)
    private String title;
    
    @ManyToOne
    @JoinColumn(name="library_id")
    private Library library;
    
    // standard constructor, getter, setter
}

public class Library {
 
    //...
 
    @OneToMany(mappedBy = "library")
    private List<Book> books;
 
    //...
 
}
```

3. Many-to-Many Relationship
using the **@ManyToMany** annotation.

* The Data Model
Example : add a new model class Author that will have a many-to-many relationship with the Book entity.

```
@Entity
public class Author {

    @Id
    @GeneratedValue
    private long id;

    @Column(nullable = false)
    private String name;

    @ManyToMany(cascade = CascadeType.ALL)
    @JoinTable(name = "book_author", 
      joinColumns = @JoinColumn(name = "book_id", referencedColumnName = "id"), 
      inverseJoinColumns = @JoinColumn(name = "author_id", 
      referencedColumnName = "id"))
    private List<Book> books;

    //standard constructors, getters, setters
}

public class Book {
 
    //...
 
    @ManyToMany(mappedBy = "books")
    private List<Author> authors;
 
    //...
}
```

## Integration Testing in Spring
![Integration Testing in Spring](https://learningarmy.com/wp-content/uploads/2021/10/image_2021-10-10_210459-623x350.png)
Spring Integration provides a number of utilities and annotations to help you test your application. Testing support is presented by two modules:

* spring-integration-test-support contains core items and shared utilities

* spring-integration-test provides mocking and application context configuration components for integration tests

1. TestUtils

The TestUtils class is mostly used for properties assertions in JUnit tests.

2. Spring MVC Test Configuration
* Enable Spring in Tests with JUnit 5

```
@ExtendWith(SpringExtension.class)
@ContextConfiguration(classes = { ApplicationConfig.class })
@WebAppConfiguration
public class GreetControllerIntegrationTest {
    ....
}
```
By adding the **@ExtendWith annotation** to our test classes and specifying the extension class to load.
We also need the **@ContextConfiguration** annotation to load the context configuration and bootstrap the context that our test will use.
And also annotate the test with** @WebAppConfiguration**, which will load the web application context.


* Mocking Web Context Beans
It encapsulates all web application beans and makes them available for testing.
Example: 

```
private MockMvc mockMvc;
@BeforeEach //We initialize the mockMvc object in the @BeforeEach annotated method so that we don't have to initialize it inside every test.

public void setup() throws Exception {
    this.mockMvc = MockMvcBuilders.webAppContextSetup(this.webApplicationContext).build();
}
```

3. Writing Integration Tests
While doing integration testing in spring boot applications, we shall keep in mind that:

* An integration test is supposed to test whether different modules are bounded correctly and if they work as expected.
* The integration tests shall not utilize the actual production dependencies and they can mimic the certain behaviors.

* The application shall run in ApplicationContext and run tests in it.
* Spring boot provides @SpringBootTest annotation which starts the embedded server, creates a web environment and then enables @Test methods to do integration testing. Use it’s webEnvironment attribute for it.
* It is recommended to use test specific configurations using @TestConfiguration annotation.

* Send GET Request With Path Variable
Example on test code :

```
@Test
public void givenGreetURIWithPathVariable_whenMockMVC_thenResponseOK() {
    this.mockMvc
      .perform(get("/greetWithPathVariable/{name}", "John"))
      .andDo(print()).andExpect(status().isOk())
      
      .andExpect(content().contentType("application/json;charset=UTF-8"))
      .andExpect(jsonPath("$.message").value("Hello World John!!!"));
}
```

### MockMvc Limitations
* MockMvc provides an elegant and easy-to-use API to call web endpoints and to inspect and assert their response at the same time.
*  Spring prepares a fake web application context to mock the HTTP requests and responses, it may not support all features of a full-blown Spring application.
* we can set up a more real application context and then use RestTemplate or even REST-assured to test our application.

#### Read more about [Integration Testing in Spring](https://www.baeldung.com/integration-testing-in-spring).



