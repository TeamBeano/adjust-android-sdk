## Integrate adjust using Eclipse.

Since SDK version 4.0.0 we recommend using Android Studio. Follow these steps to integrate the SDK using Eclipse.

## Basic Installation

The most straightforward way to integrate the adjust SDK in an Eclipse project is by linking the compiled jar.

### Get the Jar

You can get the jar in the latest [releases page][releases]. Another way is to download it from the [Maven repository][maven] 
by searching for [`com.adjust.sdk`][maven-search].

### Add the adjust library to your project

After downloading the jar file, drag it into the `libs` folder inside your project. This will make the adjust SDK available in 
your app.

### Add Google Play Services

Since the 1st of August of 2014, apps in the Google Play Store must use the [Google Advertising ID][google-ad-id] to uniquely 
identify devices. To allow the adjust SDK to use the Google Advertising ID, you must integrate the [Google Play Services]
[google-play-services]. If you haven't done this yet, follow these steps:

1. Copy the library project at

    ```
    <android-sdk>/extras/google/google_play_services/libproject/google-play-services_lib/
    ```

    to the location where you maintain your Android app projects.

2. Import the library project into your Eclipse workspace. Click `File >
   Import`, select `Android > Existing Android Code into Workspace`, and browse
   to the copy of the library project to import it.

3. In your app project, reference Google Play services library project. See
   [Referencing a Library Project for Eclipse][eclipse-library] for more
   information on how to do this.

     You should be referencing a copy of the library that you copied to your
     development workspace. You should not reference the library directly from
     the Android SDK directory.

4. After you've added the Google Play services library as a dependency for your app project, open your app's manifest file and 
   add the following tag as a child of the [<application>][application] element:

    ```xml
    <meta-data android:name="com.google.android.gms.version"
          android:value="@integer/google_play_services_version" />
    ```

### Next steps

You can follow our [guide][sdk-permissions] from the `Add permissions` section foward.

[maven]:                http://maven.org
[releases]:             https://github.com/adjust/adjust_android_sdk/releases
[application]:          http://developer.android.com/guide/topics/manifest/application-element.html
[google-ad-id]:         https://developer.android.com/google/play-services/id.html
[maven-search]:         http://search.maven.org/#search%7Cga%7C1%7Ccom.adjust.sdk
[eclipse-library]:      http://developer.android.com/tools/projects/projects-eclipse.html#ReferencingLibraryProject
[sdk-permissions]:      https://github.com/adjust/android_sdk#sdk-permissions
[google-play-services]: http://developer.android.com/google/play-services/setup.html
