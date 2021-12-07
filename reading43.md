# Amplify and Kinesis

Analytics for Android makes it simple to send your data to any tool without having to learn, test or implement a new API every time. The Analytics category enables you to collect analytics data for your App.

## Set up Analytics backend
* Run the following command in your project's root folder.
> amplify add analytics
* To deploy your backend, run:
>amplify push
amplifyconfiguration.json should be updated to reference provisioned backend analytics resources. 

## Install Amplify Libraries
* Need to add this dependencies to your app's `build.gradle`

```
dependencies {
    // Add these lines in `dependencies`
    implementation 'com.amplifyframework:aws-analytics-pinpoint:1.30.0'
    implementation 'com.amplifyframework:aws-auth-cognito:1.30.0'
}
```
* Click Sync Now.
## Initialize Amplify Analytics

```
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.addPlugin(new AWSPinpointAnalyticsPlugin(this));
```

## Record events
To record an event, create an AnalyticsEvent and call Amplify.Analytics.recordEvent() to send it:

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
### View Analytics Console
From the terminal run the following command. Navigate to the Analytics tab, and then choose View in Pinpoint.

> amplify console analytics