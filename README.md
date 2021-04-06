# react-native-feature-toggle-with-firebase

## Create Project

```bash
npx react-native init Remotine --template react-native-template-typescript
```
---

## Firebase Support

```bash
yarn add @react-native-firebase/app
```

---

### Android Setup

Firebase console -> download google-services.json and place it at:
```bash
/android/app/google-services.json
```

/android/build.gradle

```java
buildscript {
  dependencies {
    // ... other dependencies
    classpath 'com.google.gms:google-services:4.3.4'
    // Add me --- /\
  }
}
```

/android/app/build.gradle

```java
apply plugin: 'com.android.application'
apply plugin: 'com.google.gms.google-services' // <- Add this line
```

### iOS Setup

```bash
cd ios && pod install
```

Download GoogleService-Info.plist from firebase console

Copy them to project

```bash
cd ios && open Remotine.xcworkspace
```

Add GoogleService-Info.plist to project and check 'copy items if needed' box

/ios/Remotine/AppDelegate.m

```swift
#import <Firebase.h>
```

Inside *didFinishLaunchingWithOptions* method

```swift
if ([FIRApp defaultApp] == nil) {
  [FIRApp configure];
}
```

---

## Remote Config Support

```bash
yarn add @react-native-firebase/remote-config
```