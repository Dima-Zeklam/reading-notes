# Room 

## Save data in a local database using Room   
Room Database providing offline storage of data, for example Storing a list of posts (with text and images), so when a user isn’t connected, he gets to view somethings from the room database, this is the technique used in most social media apps like instagram.

### ADD DEPENDENCIES
1. Open Build.gradle file and add the necessary dependencies
2. Check `Build.gradle`(Project) and `Build.gradle`(App) for all dependencies used.
3. The dependencies used are:

```
dependencies {
    def room_version = "2.3.0"

    implementation "androidx.room:room-runtime:$room_version"
    annotationProcessor "androidx.room:room-compiler:$room_version"

    // optional - RxJava2 support for Room
    implementation "androidx.room:room-rxjava2:$room_version"

    // optional - RxJava3 support for Room
    implementation "androidx.room:room-rxjava3:$room_version"

    // optional - Guava support for Room, including Optional and ListenableFuture
    implementation "androidx.room:room-guava:$room_version"

    // optional - Test helpers
    testImplementation "androidx.room:room-testing:$room_version"

    // optional - Paging 3 Integration
    implementation "androidx.room:room-paging:2.4.0-beta01"
}
```



### There are three major components in Room:
* Database — Contains the database holder and serves as the main access point for the underlying connection to your app’s persisted, relational data.
* Entity — Represents a table within the database.
* DAO (Data access objects) — Contains the methods used for accessing the database.


![room_architecture](https://developer.android.com/images/training/data-storage/room_architecture.png)
Diagram of Room library architecture

### Database
Example on code that defines an AppDatabase class to hold the database:

```
//the class must be annotated with a @Database
@Database(entities = {User.class}, version = 1)
public abstract class AppDatabase extends RoomDatabase {
    public abstract UserDao userDao();
}
```
## Defining data using Room entities 
* you can use Room entities as a class to define your database schema that is annotated with `@Entity`.
* To make the instances of an entity uniquely identified by a combination of multiple columns by define a composite primary key by listing those columns in the primaryKeys property of @Entity.
*  To add indices to an entity, include the indices property within the @Entity annotation, listing the names of the columns that you want to include in the index or composite index:
>@Entity(indices = {@Index("name"), @Index(value = {"last_name", "address"})})

* Use `@AutoValue` annotation to include AutoValue-based objects that Room recognizes as an entit.


## Define relationships between objects

**Relations between tables: one-to-one, one-to-many and many-to-many, with one annotation: `@Relation` .**
* Sometimes, you might need to query a set of three or more tables that are all related to each other. In that case, you would define nested relationships between the tables.
* add a method to the DAO class to expose the query functionality that your app needs.
* Add  the `@Transaction` annotation when you add a method to the DAO class to ensure that the whole operation is performed atomically.



Example on one to one realtion :

```
// user entity
@Entity
public class User {
    @PrimaryKey public long userId;
    public String name;
    public int age;
}

@Entity
public class Library {
    @PrimaryKey public long libraryId;
    public long userOwnerId;
}

public class UserAndLibrary {
    @Embedded public User user;
    @Relation(
         parentColumn = "userId",
         entityColumn = "userOwnerId"
    )
    public Library library;
}

```

## Accessing data using Room DAOs 
There are two types of DAO methods that define database interactions:

1. Convenience methods that let you insert, update, and delete rows in your database without writing any SQL code.
    * insert - by using `@Insert ` which allows you to define methods that insert their parameters into the appropriate table in the database.
    * update - by using `@Update` to define methods that update specific rows in a database table.
    * Delete - by using `@Delete` annotation allows you to define methods that delete specific rows from a database table.
2. Query methods that let you write your own SQL query to interact with the database.
Example on an Query method :
 ```
 @Query("SELECT * FROM user")
public User[] loadAllUsers();
```

### Direct cursor access
**Cursor** This interface provides random read-write access to the result set returned by a database query.
