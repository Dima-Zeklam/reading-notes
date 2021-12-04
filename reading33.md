# Intent Filters

An **Intent** is a messaging object you can use to request an action from another app component. 

An **intent filter** is an expression in an app's manifest file that specifies the type of intents that the component would like to receive.

 intent filter can be fulfills the following criteria of the Intent object:
 
1. Specify one of the platform-defined values such as `ACTION_SEND` or `ACTION_VIEW` in your intent filter with the <action> element. The value you specify in this element must be the full string name for the action.
Example on an activity with an intent filter that handles the ACTION_SEND intent when the data type is either text or an image:

```
<activity android:name="ShareActivity">
    <intent-filter>
        <action android:name="android.intent.action.SEND"/>
        <category android:name="android.intent.category.DEFAULT"/>
        <data android:mimeType="text/plain"/>
        <data android:mimeType="image/*"/>
    </intent-filter>
</activity>
```

2. Specify A description of the data associated with the intent in your intent filter with the <data> element.
3. Specify `CATEGORY_DEFAULT` in your intent filter with the <category> element.

## Handle the Intent in Your Activity
* Call `getIntent()` to retrieve the Intent that started the activity. 
* You should generally do so during early callbacks such as `onCreate()` or `onStart()`.
* Call setResult() to specify the result code and result Intent.
* Call finish() to close (and destroy) your activity.

#### Read more about [Intent](https://developer.android.com/reference/android/content/Intent) , [Sharing files using intent](https://developer.android.com/training/secure-file-sharing).