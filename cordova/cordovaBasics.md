# Cordova Basics and Nuggets

```
cordova run ios --device

cordova run android --device

cordova plugin add cordova-plugin-statusbar

cordova run android —list (see all android emulators/devices)

bundle identifier has to match exactly
```

find attached USB devices: system_profiler SPUSBDataType

"failed to find Build Tools revision" error
check:
android {
    compileSdkVersion 22
    buildToolsVersion "22.0.0"
}

Building an Android platform release:
http://developer.android.com/tools/building/building-studio.html