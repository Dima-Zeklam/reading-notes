# GraphQL @connection

## AWS AppSync-provided directives
AWS AppSync provides a robust, scalable GraphQL interface for application developers to combine data from multiple sources, including Amazon DynamoDB, AWS Lambda, and HTTP APIs.

![AWS AppSync-provided Architecture](https://docs.aws.amazon.com/appsync/latest/devguide/images/systemoverview.png)

**AWS AppSync includes a variety of features :**
* Integration with Amazon Cognito user pools for fine-grained access control at a per-field level
* Efficient data caching
* Powerful GraphQL schema editing through the AWS AppSync console, including automatic GraphQL schema generation from DynamoDB.

### @connection
The @connection directive enables you to specify relationships between @model types. Currently, this supports one-to-one, one-to-many, and many-to-one relationships. 

### Definition

> directive @connection(keyName: String, fields: [String!]) on FIELD_DEFINITION

### Connection Specification
To ensure a consistent implementation of this pattern, the Relay project has a formal specification you can follow for building GraphQL APIs which use a cursor based connection pattern.