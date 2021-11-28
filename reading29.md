
# Amplify Auth
Amplify Auth lets you quickly set up secure authentication flows with a fully-managed user directory.  Control what users have access to in your mobile and web apps with Amplify Auth's built-in authorization capabilities.

## Configure Auth Category
To start you need to execute the command:
> amplify add auth
To push your changes to the cloud, execute the command:
> amplify push

## Install Amplify Libraries
Need to add this dependencies  to your app's `build.gradle`
```
dependencies {
    implementation 'com.amplifyframework:aws-auth-cognito:1.30.0'
}
```

## Initialize Amplify Auth
**Add this line, to include the Auth plugin.**

```
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.configure(getApplicationContext());
```
## Check the current auth session
 run this from your MainActivity's `onCreate` method.

 ```
 Amplify.Auth.fetchAuthSession(
    result -> Log.i("AmplifyQuickstart", result.toString()),
    error -> Log.e("AmplifyQuickstart", error.toString())
);
```
## Register a user
1.  The default CLI requires a **username**, **password** and a valid **email id** as parameters to register a user.
2.  Invoke the following api to initiate a sign up flow:

```
AuthSignUpOptions options = AuthSignUpOptions.builder()
    .userAttribute(AuthUserAttributeKey.email(), "my@email.com")
    .build();
Amplify.Auth.signUp("username", "Password123", options,
    result -> Log.i("AuthQuickStart", "Result: " + result.toString()),
    error -> Log.e("AuthQuickStart", "Sign up failed", error)
);
```

3. confirm the user. A confirmation code will be sent to the email id provided during sign up.
```
Amplify.Auth.confirmSignUp(
    "username",
    "the code you received via email",
    result -> Log.i("AuthQuickstart", result.isSignUpComplete() ? "Confirm signUp succeeded" : "Confirm sign up not complete"),
    error -> Log.e("AuthQuickstart", error.toString())
);
```

3. When you see the following in your console window: `Confirm signUp succeeded` that mean sign up flow is complete


4. Implement a UI to get the username and password from the user.

5. Start the sign in flow by calling the following method:

```
Amplify.Auth.signIn(
    "username",
    "password",
    result -> Log.i("AuthQuickstart", result.isSignInComplete() ? "Sign in succeeded" : "Sign in not complete"),
    error -> Log.e("AuthQuickstart", error.toString())
);
```
6.  When you see the following in your console window: `Sign in succeeded` that mean You have now successfully registered a user and authenticated with that user's username and password with Amplify.

### See More About [AUTHENTICATION In Android](https://docs.amplify.aws/lib/auth/getting-started/q/platform/android/)
