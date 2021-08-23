# Mongo and Mongoose

### Fill in the chart below with five differences between SQL and NoSQL databases:
![SQL vs NoSQL](https://codersera.com/blog/wp-content/uploads/2019/12/SQL-VS-NoSQL-1.jpg)

SQL        |  NoSQL
-----------|---------------
Relational Databases (RDBMS) | non-relational or distributed database
SQL databases are table based databases|document based, key-value pairs, graph databases or wide-column stores
have predefined schema| ave dynamic schema for unstructured data
vertically scalable| horizontally scalable
scaled by increasing the horse-power of the hardware | scaled by increasing the databases servers in the pool of resources to reduce the load
<!-- uses SQL ( structured query language ) for defining and manipulating the data | queries are focused on collection of documents. Sometimes it is also called as UnQL (Unstructured Query Language)
SQL database examples: MySql, Oracle, Sqlite, Postgres and MS-SQL | NoSQL database examples: MongoDB, BigTable, Redis, RavenDb, Cassandra, Hbase, Neo4j and CouchDb
QL databases are good fit for the complex query intensive environment | NoSQL don’t have standard interfaces to perform complex queries -->


### What kind of data is a good fit for an SQL database?
complex query intensive environment
### Give a real world example.
MySql, Oracle, Sqlite, Postgres and MS-SQL
### What kind of data is a good fit a NoSQL database?
NoSQL database fits better for the hierarchical data storage as it follows the key-value pair way of storing data similar to JSON data. NoSQL database are highly preferred for large data set 
### Give a real world example.
MongoDB, BigTable, Redis, RavenDb, Cassandra, Hbase, Neo4j and CouchDb
### Which type of database is best for hierarchical data storage?
NoSQL databases, make up for an excellent option for storing data in a hierarchical database model.

### Which type of database is best for scalability? 
NoSQL databases have the ability to become larger and much more powerful, making them the preferred choice for large or constantly evolving data sets.

### What does SQL stand for?
SQL stands for Structured Query Language
### What is a realational database?
A relational database is a type of database that stores and provides access to data points that are related to one another. Relational databases are based on the relational model, an intuitive, straightforward way of representing data in tables.

### What type of structure does a relational database work with?
logical data structures—the data tables, views, and indexes
### What is a ‘schema’?
is a set of formulas (sentences) called integrity constraints imposed on a database
### What is a NoSQL database?
A NoSQL database provides a mechanism for storage and retrieval of data that is modeled in means other than the tabular relations used in relational databases
### How does it work?
Behind-the-scenes, they use a keyspace to distribute your data across multiple servers or partitions. This allows them to scale horizontally across many thousand servers.
NoSQL databases can operate in multiple modes: as key-value store, document store or wide column store.

![Mongo database](https://marvel-b1-cdn.bc0a.com/f00000000173332/www.openlogic.com/sites/openlogic/files/image/2021-06/image-blog-openlogic-what-is-mongodb.png)
### What is inside of a Mongo database?
MongoDB stores data records as documents (specifically BSON documents) which are gathered together in collections. A database stores one or more collections of documents.

### Which is more flexible - SQL or MongoDB? and why.
MongoDB is more flexible, because MongoDB can be used by businesses and organizations of all sizes who are looking to scale out huge volumes of traffic as well as data. If you desire great speed and certain flexibility with the use of unstructured data within a schemaless environment, MongoDB is your go-to.  

### What is the disadvantage of a NoSQL database?
* NoSQL databases don’t have the reliability functions which Relational Databases have (basically don’t support ACID)
* NoSQL are very new compared to Relational Databases, which means that are far less stable and may have a lot less functionalities.

## Things I want to know more about
* DynamoDB, Berkeley DB.
* more about how to use Mongo database.

