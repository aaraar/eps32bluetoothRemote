# eps32bluetoothRemote
A react-native bluetooth remote for an esp32

## Purpose of this project
Currently I am tinkering around with ESP32 and I would like to try and make a simple skeleton for sending basic BT messages to the microcontroller
I am a student, and am following an IoT class that only covers the basics of the arduino IDE and therefore would like to make something that is not covered.
The react-native part of this project will be VERY basic, since I have no prior experience

## What you need
- Arduino IDE with ESP32 board support installed
- Android Studio set up with the right SDK's for your device (I already had done this prior, I recommend the tutorial on https://facebook.github.io/react-native/docs/getting-started.html)
- ESP32 (I have a DOIT DEVKIT V1)
- An Android/iOS phone or a virtual phone (can also be found on the aforementioned link)

## How to recreate this project (School assignment)
1. Create a folder for your project
2. Open Android studio and open that folder using "Open existing project"
3. Open the terminal and run `react-native init PROJECT_NAME --version react-native@next` and replace PROJECT_NAME with your project name
4. Run `npm i react-native-ble-plx`
5. Run `react-native link react-native-ble-plx`
6. Open build.gradle of app module make sure that min SDK version is at least 18:
```
android {
    ...
    defaultConfig {
        minSdkVersion 18
        ...
```
7. In AndroidManifest.xml, add Bluetooth permissions and update `<uses-sdk/>`:

```
    <manifest xmlns:android="http://schemas.android.com/apk/res/android"
    ...
    <uses-permission android:name="android.permission.BLUETOOTH"/>
    <uses-permission android:name="android.permission.BLUETOOTH_ADMIN"/>
    <uses-permission-sdk-23 android:name="android.permission.ACCESS_COARSE_LOCATION"/>

    <!-- Add this line if your application always requires BLE. More info can be found on:
         https://developer.android.com/guide/topics/connectivity/bluetooth-le.html#permissions
      -->
    <uses-feature android:name="android.hardware.bluetooth_le" android:required="true"/>

    <uses-sdk
        android:minSdkVersion="18"
        ...
        
 ````
You have now set up a react-native app and linked a bluetooth library
