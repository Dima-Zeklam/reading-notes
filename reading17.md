# Many to many relationships & Web App Security

### many-to-many relationship
many-to-many relationship is  a connection between two types of entities. both sides can relate to multiple instances of the other side.

![manyToMany](https://www.baeldung.com/wp-content/uploads/2017/09/New.png)

In this example the employee may have multiple projects and the project may have many employee, we need to create a separate table to hold the foreign keys. Such a table is called a join table. In the example above a join table employee_project is required here to connect both side.
We can map a many-to-many association with JPA annotations by useing the @ManyToMany, @JoinTable and @JoinColumn annotations

```
 @ManyToMany(cascade = { CascadeType.ALL })
    @JoinTable(
        name = "Employee_Project", 
        joinColumns = { @JoinColumn(name = "employee_id") }, 
        inverseJoinColumns = { @JoinColumn(name = "project_id") }
    )
    Set<Project> projects = new HashSet<>();
```
both the Employee class and Project classes refer to one another, which means that the association between them is functioning in two directions.


## This World of Ours

The article [This World of Ours](https://scholar.harvard.edu/files/mickens/files/thisworldofours.pdf) includes stories and real-life examples about the danger that we may face because of the weak security for our accounts,  using Dangerous Websites or get untrust email and other, which may lead to steal the personal information and use it in a way that will damage the owner and more. 
So one of the thigs we need to pay attention to is to make the PASSWORD stronger, here are some advices to Creating strong passwords: 

1. Never use sequential numbers or letters, and for the love of all things cyber, do not use “password” as your password.
2. Use a mix of characters and Make it long.
3. Do not use sequential keyboard paths either (like qwerty). These are among the first to be guessed.
4. Never use personal information such as your name, birthday, user name, or email address
5. Don't use the same password for each account. 
6. Random passwords are the strongest. If you're having trouble creating one, you can use a [password generator](https://privacycanada.net/strong-password-generator/) instead.



