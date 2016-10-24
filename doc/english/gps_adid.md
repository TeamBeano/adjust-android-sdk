# Google Advertising Id

The default behavior of the Android SDK of adjust is to send the [Google Advertising ID][google-ad-id] when it's available. 
Only if the app does not use [Google Play Services][google-play-services], we try to obtain the Android Id and Mac Address of 
the device.

Although we have this protection to prevent the use of MAC Address or Android Id for an app which uses Google Play Services, 
it's possible to remove from the source the files that access this device functions. Follow the steps to do so:

1. Get the Android SDK of adjust by following the first step of our [guide][get-sdk].

2. Find the folder `adjust/src/main/java/com/adjust/sdk/plugin`. It contains both the files `MacAddressUtil.java` and   
   `AndroidIdUtil.java`.

3. Delete one or both files, that you don't want to be used in any case from the project.

[get-sdk]:                https://github.com/adjust/android_sdk#sdk-get
[google-ad-id]:           https://developer.android.com/google/play-services/id.html
[google-play-services]:   http://developer.android.com/google/play-services/setup.html#ensure
