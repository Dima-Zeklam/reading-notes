# Amazon S3
![Amazon S3](https://miro.medium.com/max/640/1*B9CIOrxdROHvtdmouQA1_A.png)
Amazon Simple Storage Service (Amazon S3) is a scalable, high-speed, web-based cloud storage service. The service is designed for online backup and archiving of data and applications on Amazon Web Services (AWS).


## Amazon S3 features
* Data can be transferred to S3 over the public internet via access to S3 application programming interfaces (APIs).
* Provides functionality to simplify manageability of data through its lifetime. Includes options for segregating data by buckets, monitoring and controlling spend, and automatically archiving data to even lower cost storage options.
* Uses standards-based REST and SOAP interfaces designed to work with any Internet-development toolkit.
* capabilities to append metadata tags to objects, move and store data across the S3 Storage Classes, configure and enforce data access controls, secure data against unauthorized users, run big data analytics, and monitor data at the object and bucket levels. 

## How Amazon S3 works
Amazon S3 is an object storage service, which differs from other types of cloud computing storage types, such as block and file storage. Each object is stored as a file with its metadata included. The object is also given an ID number

## Provision backend storage
To start provisioning storage resources in the backend execute the command:

>amplify add storage

After that execute the command:

>amplify push


## Install Amplify Libraries
Need to add this dependencies  to your app's `build.gradle`
```
dependencies {
    implementation 'com.amplifyframework:aws-storage-s3:1.30.0'
    implementation 'com.amplifyframework:aws-auth-cognito:1.30.0'
}
```
## Initialize Amplify Storage

Add the following code to your `onCreate()` method in your application class:

```
   try {
            // Add these lines to add the AWSCognitoAuthPlugin and AWSS3StoragePlugin plugins
            Amplify.addPlugin(new AWSCognitoAuthPlugin());
            Amplify.addPlugin(new AWSS3StoragePlugin());
            Amplify.configure(getApplicationContext());

            Log.i("MyAmplifyApp", "Initialized Amplify");
        } catch (AmplifyException error) {
            Log.e("MyAmplifyApp", "Could not initialize Amplify", error);
        }
    }
```
## Uploading data to your bucket
By setting this method in your activity: 
```
private void uploadFile() {
    File exampleFile = new File(getApplicationContext().getFilesDir(), "ExampleKey");

    try {
        BufferedWriter writer = new BufferedWriter(new FileWriter(exampleFile));
        writer.append("Example file contents");
        writer.close();
    } catch (Exception exception) {
        Log.e("MyAmplifyApp", "Upload failed", exception);
    }

    Amplify.Storage.uploadFile(
            "ExampleKey",
            exampleFile,
            result -> Log.i("MyAmplifyApp", "Successfully uploaded: " + result.getKey()),
            storageFailure -> Log.e("MyAmplifyApp", "Upload failed", storageFailure)
    );
}
```

### For More information visit [Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)