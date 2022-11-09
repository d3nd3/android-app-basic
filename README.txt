https://developer.android.com/studio/releases/gradle-plugin

match android gradle plugin version with gradle version

https://stackoverflow.com/questions/19911762/what-are-the-android-sdk-build-tools-platform-tools-and-tools-and-which-versio
about build tools


Download SDK versions with:
https://developer.android.com/studio/index.html#command-tools


c:\users\dende\desktop\android\cmdline-tools\tools\bin
c:\users\dende\desktop\android\android-sdk

Android/tools/bin/sdkmanager.bat

cmd.exe /c sdkmanager.bat "platforms;android-7"
cmd.exe /c sdkmanager.bat "build-tools;30.0.1"
cmd.exe /c sdkmanager.bat "platform-tools"

@local.properties project root
sdk.dir=/mnt/c/Users/dende/Desktop/Android


Every app project must have an AndroidManifest.xml file (with precisely that name) at the root of the project source set. The manifest file describes essential information about your app to the Android build tools, the Android operating system, and Google Play.    BELONGS IN HOME/src/main

https://developer.android.com/studio/releases/gradle-plugin#3-1-0