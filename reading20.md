# Intents, Activities, and SharedPreferences

## Tasks and the back stack
A task is a collection of metadata and information around a stack of activities.
The activities are stacked in the order in which they are opened in a stack called the back stack.

One action in an email app, for example, maybe to display a list of fresh messages. When the user picks a message, a new activity appears in which the user may read the message. This new action has been sent to the back of the queue. When the user clicks the Back button, the new action is completed and removed from the stack.


![diagram_backstack](https://developer.android.com/images/fundamentals/diagram_backstack.png)

*  When you start a new activity using startActivity(), that is by default pushing a new activity onto your task, causing the previous Activity to be paused (and stopped if the new activity fully obscures the previous activity)


* **Root launcher activities** act as entry points into your app from the app launcher and are used to start a task.

* Foreground tasks include periodic tasks and background tasks include sporadic and aperiodic tasks

### Starting a task
You can set up an activity as the entry point for a task by giving it an intent filter with "android.intent.action.MAIN" as the specified action and "android.intent.category.LAUNCHER" as the specified category. For example:

```
<activity ... >
    <intent-filter ... >
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>
    ...
</activity>
```

## Save key-value data 
You should use the `SharedPreferences` APIs
If you have a relatively small collection of key-values that you'd like to save, `SharedPreferences` is an interface for  accessing and modifying preference data returned by Context.getSharedPreferences(String, int).

### Get a handle to shared preferences
* `getSharedPreferences()` — for multiple shared preference files identified by name.
* `getPreferences()` —  if you need to use only one shared preference file for the activity. 

**Example on Shared Preferences:**

```
Context context = getActivity();
SharedPreferences sharedPref = context.getSharedPreferences(
        getString(R.string.preference_file_key), Context.MODE_PRIVATE);

// if you need just one shared preference file for your activity, you can use the getPreferences() method:
        SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);

```

## Write to shared preferences
Pass the keys and values for Example :

```
SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
SharedPreferences.Editor editor = sharedPref.edit();
editor.putInt(getString(R.string.saved_high_score_key), newHighScore);
editor.apply();

```
* Call apply() or commit() to save the changes.


