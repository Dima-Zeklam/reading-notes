# Android fundamentals

## Android 
**Android** is a mobile operating system designed primarily for touchscreen mobile devices such as smartphones and tablets. It is free and open-source software. It was unveiled in November 2007, written in Java (UI), C (core), C++ and others, developed by a consortium of developers known as the Open Handset Alliance and commercially sponsored by Google.

![Android](https://www.android.com/static/2016/img/share/n-sm.png)

## Android apps
Android apps can be written using Kotlin, Java, and C++ languages" using the Android software development kit (SDK), while using other languages is also possible.The Android SDK (Software development kit) tools compile your code along with any data and resource files into an APK(Android application package) or an Android App Bundle.

## Android security features:
Android has built-in security features that significantly reduce the frequency and impact of application security issues.
* An encrypted file system that can be enabled to protect data on lost or stolen devices.
* User-granted permissions to restrict access to system features and user data.
* Android assigns a unique user ID (UID) to each Android app and runs it in its own process. Android uses this UID to set up a kernel-level App Sandbox.
* The Android Application Sandbox, which isolates your app data and code execution from other app.

## App components


Components |	Description
---------- | --------------
Activities	| They dictate the UI and handle the user interaction to the smart phone screen
Services |	They handle background processing associated with an application.
Broadcast |  Receivers	They handle communication between Android OS and applications.
Content Providers |	They handle data and database management issues.

## The manifest file
* The manifest file provides essential information about your app to the Android operating system.
* The Android manifest file helps to declare the permissions that an app must have to access data from other apps.
* Declares hardware and software features used or required by the app, such as a camera, bluetooth services, or a multitouch screen.

* Declares API libraries the app needs to be linked against (other than the Android framework APIs), such as the Google Maps library.
* Declares the minimum API Level required by the app

#### Example on manifest file can declare an activity 

```
<?xml version="1.0" encoding="utf-8"?>
<manifest ... >
    <application android:icon="@drawable/app_icon.png" ... >
        <activity android:name="com.example.project.ExampleActivity"
                  android:label="@string/example_label" ... >
        </activity>
        ...
    </application>
</manifest>
```
#### You can declare an intent filter for your component by adding an *intent-filter* element as a child of the component's declaration element.

```
<manifest ... >
    ...
    <application ... >
        <activity android:name="com.example.project.ComposeEmailActivity">
            <intent-filter>
                <action android:name="android.intent.action.SEND" />
                <data android:type="*/*" />
                <category android:name="android.intent.category.DEFAULT" />
            </intent-filter>
        </activity>
    </application>
</manifest>
```
* Read more about [Android apps](https://developer.android.com/guide/components/fundamentals)