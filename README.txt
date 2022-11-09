gradlew is like a wrapper for gradle, the same way pyenv is a wrapper for python

switching gradle versions with
gradle wrapper --gradle-version 5.4.1

apt install android-sdk
export ANDROID_HOME=/usr/lib/android-sdk


command line tools
  https://developer.android.com/studio#command-tools

 make folder:
   /usr/lib/android-sdk/cmdline-tools/latest
   copy contents that just downloaded into it.


sudo su
nano ~/.bashrc
export ANDROID_HOME=/usr/lib/android-sdk
export PATH=$ANDROID_HOME/cmdline-tools/latest/bin:/opt/gradle/gradle-7.5.1/bin:$PATH

https://gradle.org/install/#manually
mkdir /opt/gradle
unzip -d /opt/gradle gradle-7.5.1-bin.zip



the sdkmanager java app will want to write to there, so needs root.
sdkmanager "platforms;android-7"
sdkmanager "build-tools;30.0.3"
sdkmanager "build-tools;27.0.3"
sdkmanager "platform-tools"

The Android Gradle Plugin is what makes the gradle 'make' system work specifically for android projects.
Each version has a minimum requirement of actual Gradle and android build-tools.

To find the Android Gradle Plugin version : 
  gradle buildEnvironment | grep com.android.tools.build:gradle:

dependencies {
        classpath 'com.android.tools.build:gradle:3.1.0'
    }

this line is inside build.gradle is defining the gradle plugin version to use.
So you search here for the version requirements of build-tools and Gradle.
https://developer.android.com/studio/releases/gradle-plugin#3-1-0

@local.properties project root
sdk.dir=/mnt/c/Users/dende/Desktop/Android

Every app project must have an AndroidManifest.xml file (with precisely that name) at the root of the project source set. The manifest file describes essential information about your app to the Android build tools, the Android operating system, and Google Play.    BELONGS IN HOME/src/main


gradle tasks

gradle assembleDebug


Not supported on arm64/arm.
AAPT2 daemon faiing to runu linux
attempting to disable AAPT2, gradle.properties , android.enableAapt2=false
build.gradle , android {
    aaptOptions.cruncherEnabled = false
    aaptOptions.useNewCruncher = false

