# Location 

Use the fused location provider to retrieve the device’s last known location. The fused location provider is one of the location APIs in Google Play services. It manages the underlying location technology and provides a simple API so that you can specify requirements at a high level, like high accuracy or low power. It also optimizes the device’s use of battery power.


## Set up Google Play services
### What is Google Play Services?
Google Play Services connects apps to other Google services, like Google Sign In and Google Maps. Google Play Services isn’t the same as the Google Play Store app, and is included with Android.

To access the fused location provider, your app’s development project must include Google Play services. Download and install the Google Play services component via the SDK Manager and add the library to your project:
1. For each SDK that your app requires, include the dependency for that SDK, in build.gradle file inside your app's module directory set these dependencies for Android apps which includes a section that lists common Google Play services 

```
apply plugin: 'com.android.application'

...

dependencies {
    implementation 'com.google.android.gms:play-services-location:18.0.0'
}
```
2. Save the changes and sync your project.

## Specify app permissions 
Apps whose features use location services must request location permissions, depending on the use cases of those features.
To request the last known location, call the `getLastLocation()` method.

```
Example :
    fusedLocationClient.getLastLocation()
            .addOnSuccessListener(this, new OnSuccessListener<Location>() {
                @Override
                public void onSuccess(Location location) {
                    // Got last known location. In some rare situations this can be null.
                    if (location != null) {
                        // Logic to handle location object
                    }
                }
            });
```

**You need to add these permissions to your manifest file:**

```
<manifest ... >
  <!-- To request foreground location access, declare one of these permissions. -->
  <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
  <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
</manifest>
```
## Get the last known location:
- After creating location service the location can get by this method "getLastLocation()".
- You can detrmine the precision  of location returned by setting on manifest file.
- This code represent location request and response.

```
   fusedLocationClient.getLastLocation()
        .addOnSuccessListener(this, new OnSuccessListener<Location>() {
            @Override
            public void onSuccess(Location location) {
                // Got last known location. In some rare situations this can be null.
                if (location != null) {
                    // Logic to handle location object
                }
            }
        });

```
- The getLastLocation() method returns a Task that you can use to get a Location object with the latitude and longitude coordinates of a geographic location.
- Location is turned off in the device settings. so location may be null.
- The device never recorded its location.
- Google Play services on the device has restarted ,nd there is no active Fused Location Provider client that has requested location ,so you should create new client and request location update.



