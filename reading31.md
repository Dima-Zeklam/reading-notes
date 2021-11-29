# Amazon Simple Notification Service (Amazon SNS) 
## What is Amazon SNS?
Is a cloud service for coordinating the delivery of push messages from software applications to subscribing endpoints and clients. All messages published to Amazon SNS are warehoused across several availability zones to prevent loss.
![Amazon SNS](https://docs.aws.amazon.com/sns/latest/dg/images/sns-delivery-protocols.png)
## The benefits of using Amazon SNS
1. Instantaneous, push-based delivery (no polling)
2. Simple APIs and easy integration with applications
3. Flexible message delivery over multiple transport protocols
4. Inexpensive, pay-as-you-go model with no up-front costs
5. Web-based AWS Management Console offers the simplicity of a point-and-click interface.

## Amazon Simple Notification Service
* The A2A pub/sub functionality provides topics for high-throughput, push-based, many-to-many messaging between distributed systems, microservice, and event-driven serverless applications.

* The A2P functionality enables you to send messages to users at scale via SMS, mobile push, and email. 
* Is a fully managed messaging service for both application-to-application (A2A) and application-to-person (A2P) communication.
* Fully managed pub/sub messaging, SMS, email, and mobile push notifications.
* Using Amazon SNS topics, your publisher systems can fan out messages to a large number of subscriber systems including Amazon SQS queues, AWS Lambda functions and HTTPS endpoints, for parallel processing, and Amazon Kinesis Data Firehose.

## Prerequisites
* Step 1: Create a topic, topic is a logical access point that acts as a communication channel.
* Step 2: Create a subscription to the topic
* Step 3: Publish a message to the topic
* Step 4: Delete the subscription and topic

## Common Amazon SNS scenarios
### Application integration
 is a fast, flexible, fully managed push messaging service. Use SNS to push notifications to internet-connected smart devices, as well as other distributed services.


### Application alerts
is used to notify users when new content is available that matches a predefined, for example you can receive immediate notification when an event occurs, such as a specific change to your Amazon EC2 Auto Scaling group, a new file uploaded to an Amazon S3 bucket, or a metric threshold breached in Amazon CloudWatch. 


## What is SNS used for?
* Sending events to mobile clients via **push notifications** Mobile, push notifications can be useful for sending secure, time-sensitive updates to your users. 

* Sending events between system elements that don't require exactly-once processing While Amazon SQS, a related AWS service, is a good fit for distributing work in units that need to be performed exactly once, SNS is a better option for distributing the information across systems where exactly-once delivery is not as important.

* A common solution for such cases is to use SNS with two SQS queues as subscribers. SQS guarantees that each message is only processed once, and SNS allows you to send the same message to multiple clients. 

* One-to-many notifications In using different queueing systems, you might find that you need to send a message into multiple read-once queues.

* Sending transactional email or SMS notifications Many companies need to keep their customers up to date on what’s happening with their accounts, orders, posts, and so on.




