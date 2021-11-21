# Serverless and Amplify

### Serverless
Is a cloud-native development model that allows developers to build and run applications without having to manage servers.

### Function as a service (FaaS)
Is an event-driven cloud-based systems provides a platform allowing customers to develop, run, and manage application functionalities without the complexity of building and maintaining the infrastructure.

### Traditional vs. Serverless Architecture
1. Pricing - Serverless is reduced cost (The winner here is Serverless Architecture)
2. Networking - Serverless functions are accessed only as private APIs. To access these you must set up an API Gateway. (The winner here is Traditional Architecture)
3. 3rd Party Dependencies - based on the context,simple applications with few dependencies, Serverless is the winner; for anything more complex, Traditional Architecture is the winner.
4. Environments - Setting up different environments for Serverless is as easy as setting up a single environment. The winner here is Serverless Architecture)
5. Timeout - A hard limit on this time makes Serverless unusable for applications that have variable execution times.(The winner here is Traditional Architecture)
6. Scale - It’s a tie between Serverless and Traditional Architecture.

### Lambda
Lambda is a compute service that lets you run code without provisioning or managing servers. 

![Lambda](https://stackify.com/wp-content/uploads/2018/03/AWS-Lambda-serverless-computing-881x441.png)

### advantages and disadvantages of serverless architecture
Advantages of serverless computing |	Disadvantages of serverless computing
-----------------------------------|---------------------------------------
The provider scales and manages the required resources|	No access to virtual machines, operating system or runtime environments 
Rapid provision of resources in real-time, even for unforeseen peak loads and disproportionate growth	| Implementing serverless structures is very labor-intensive
Users are only charged for the resources used	| Lock-in effect – for example, when changing provider, you generally have to recode all event-based functions
High error tolerance thanks to flexible hardware infrastructure in the provider’s computer centers	| Relatively complex monitoring and debugging process, as in-depth performance, and error analyses are generally not possible

##  GraphQL Transform
A tool to transform GraphQL schemas via simple functions, Navigate into the root of  Android project and run: `amplify init`

Read more about [GraphQL Transform](https://docs.amplify.aws/cli/graphql-transformer/overview/#update-schema)



