# Amplify and Kinesis
![Amplify](https://cdn-ssl-devio-img.classmethod.jp/wp-content/uploads/2020/05/amplify-using-service-640x386.png)
## Analytics
Enables you to collect analytics data for your App. 

## Prerequisites
### Set up Analytics backend
* Run the following command in your project's root folder.
> amplify add analytics
* To deploy your backend, run:
>amplify push

### Install Amplify Libraries
Need to add this dependencies to your app's `build.gradle`

```
dependencies {
    // Add these lines in `dependencies`
    implementation 'com.amplifyframework:aws-analytics-pinpoint:1.30.0'
    implementation 'com.amplifyframework:aws-auth-cognito:1.30.0'
}
```

### Initialize Amplify Analytics
```
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.addPlugin(new AWSPinpointAnalyticsPlugin(this));
```
### Recording an event
create an AnalyticsEvent and call Amplify.Analytics.recordEvent() to send it:

```
AnalyticsEvent event = AnalyticsEvent.builder()
    .name("PasswordReset")
    .addProperty("Channel", "SMS")
    .addProperty("Successful", true)
    .addProperty("ProcessDuration", 792)
    .addProperty("UserAge", 120.3)
    .build();

Amplify.Analytics.recordEvent(event);
``` 

### Configure Your App
Import and load the configuration file in your app

```
import Amplify, { Analytics } from 'aws-amplify';
import awsconfig from './aws-exports';
Amplify.configure(awsconfig);
```

### View Analytics Console
From the terminal run the following command. Navigate to the Analytics tab, and then choose View in Pinpoint.

> amplify console analytics


## Amazon Kinesis Data 
Streams is a fully managed service for real-time processing of streaming data at massive scale,  you can build real-time dashboards, capture exceptions and generate alerts, drive recommendations, and make other real-time business or operational decisions. 

### Amazon Kinesis Data Firehose
 With Kinesis Data Firehose,you configure your data producers to send data to Firehose and it automatically delivers the data to the destination that you specified.

### Integrating Amazon Kinesis

* Need to add this dependencies to your app's `build.gradle`
 ```
dependencies {
  //enables sending analytics to Amazon Kinesis.
  implementation 'com.amazonaws:aws-android-sdk-kinesis:2.36.0'
  //  gives access to the AWS credentials provider and configurations.
  implementation 'com.amazonaws:aws-android-sdk-mobile-client:2.36.0'
}
```
* Add the following imports to the main activity of your app.

```
import com.amazonaws.mobileconnectors.kinesis.kinesisrecorder.*;
import com.amazonaws.mobile.client.AWSMobileClient;
import com.amazonaws.regions.Regions;
```
* to allows the user to submit records to a specific data stream use the following IAM policy:

```
{
    "Statement": [{
        "Effect": "Allow",
        "Action": "kinesis:PutRecords",
        "Resource": "arn:aws:kinesis:us-west-2:111122223333:stream/mystream"
    }]
}
```
4. To allows the user to submit records to a specific Kinesis Data Firehose delivery stream use the following IAM policy:

```
{
    "Statement": [{
        "Effect": "Allow",
        "Action": "firehose:PutRecordBatch",
        "Resource": "arn:aws:firehose:us-west-2:111122223333:deliverystream/mystream"
    }]
}
```




