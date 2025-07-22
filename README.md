## React Native Android Setup Guide

### Create Project

```bash
npx @react-native-community/cli init firstApp
```

//////////////////////////////////////////////////////////////

### Clear Cache

```bash
npx react-native start --reset-cache
```

//////////////////////////////////////////////////////////////

### Start Metro & Run Project

```bash
npx react-native start --reset-cache
npx react-native run-android  # For Android
npx react-native run-ios      # For iOS (if applicable)
```

//////////////////////////////////////////////////////////////

### Clean Gradle

```bash
cd android
./gradlew clean
```

//////////////////////////////////////////////////////////////

### Run Project

```bash
npx react-native run-android
# OR
npx react-native start
```

//////////////////////////////////////////////////////////////

### Build APK

```bash
cd android
./gradlew assembleRelease
```

//////////////////////////////////////////////////////////////

### Create Local Properties File

File: `/android/local.properties`

```properties
sdk.dir=/Users/username/Library/Android/sdk  # macOS
sdk.dir=C:\\Users\\username\\AppData\\Local\\Android\\Sdk  # Windows
```

//////////////////////////////////////////////////////////////

### Generate Separate APKs by ABI

Add to `/android/app/build.gradle`

```gradle
android {
    splits {
        abi {
            enable true
            reset()
            include 'armeabi-v7a', 'arm64-v8a', 'x86', 'x86_64'
            universalApk false
        }
    }
}
```

//////////////////////////////////////////////////////////////

### Bypass PowerShell Policy

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

//////////////////////////////////////////////////////////////

### Figma Design Link

[LDESK 3.0 Design](https://www.figma.com/design/4lLmcGAZzD0SG0UucAfCfB/LDESK-3.0?node-id=6-2063&p=f&t=OePhROTvGSQirOPT-0)

//////////////////////////////////////////////////////////////

### Clear Cache and Session Data in React Native

```js
import AsyncStorage from '@react-native-async-storage/async-storage';
import { useEffect } from 'react';

useEffect(() => {
  const clearStorage = async () => {
    await AsyncStorage.clear();
    console.log('AsyncStorage cleared!');
  };

  clearStorage();
}, []);
```

//////////////////////////////////////////////////////////////

### ADB & Environment Setup

```bash
# Get platform-tools
# Add platform-tools to system environment PATH

adb devices
adb tcpip 5555
adb connect 192.168.1.5:5555
adb devices
```

### Java Setup

* Install Java 17
* Add system environment:

  * Name: `JAVA_HOME`
  * Value: `C:\jdk-17.0.15+6`
* Add to `Path`:

  ```
  %JAVA_HOME%\bin
  ```

### Install Android Studio

* Set SDK location in `/android/local.properties`:

  ```
  sdk.dir=C:\Users\vishn\AppData\Local\Android\Sdk
  ```
