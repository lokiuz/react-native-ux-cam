# react-native-ux-cam

## Installation
`$yarn add file:/path-to-the-uxcam-react-wrapper`

`$react-native link react-native-ux-cam`

## Usage
```javascript
import RNUxcam from 'react-native-ux-cam';

RNUxcam.startWithKey('YOUR API KEY');
```
# For testing example app
## Setup
`yarn install`

`yarn add react-native-ux-cam`
### or if adding locally
`yarn add file:/path-to-uxcam-plugin`

## Add the key from UXCam to App.js file

## Running
`react-native run-android`

`react-native run-ios`

# Manual Installation
## Setup

```bash
# Yarn
yarn add react-native-ux-cam

# NPM
npm install --save react-native-ux-cam
```

### iOS with react-native and Cocoapods

Add the following to your Podfile:

```ruby
pod 'RNUxcam', path: "../node_modules/react-native-ux-cam", :podspec => "../node_modules/react-native-ux-cam/ios/RNUxcam.podspec"
```

Then run:

```bash
pod install
```

### Android

1.
Go to `android/settings.gradle`
add `include ':react-native-ux-cam'`
and on the following line add `project(':react-native-ux-cam').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-ux-cam/android')` 

2.
Go to `android/app/build.gradle`
add `compile project(':react-native-ux-cam')` under dependencies

3.
Go to `android/app/src/main/java/com/terravion/dbug/MainApplication.java`
add `import com.rnuxcam.rnuxcam.UXCamPackage;`

4.
Add the following to your file `android/app/build.gradle` (or add the maven url to your existing repositories section):

```gradle
allprojects {
    // All of React Native (JS, Obj-C sources, Android binaries) is installed from npm
    maven { url "$rootDir/../node_modules/react-native/android" }
    maven { url "http://sdk.uxcam.com/android/" }
}
```

5.
And add this to your file `android/app/src/main/AndroidManifest.xml`, inside your `<application>` tag:

```xml
<service android:name="com.uxcam.service.HttpPostService"/>
```
## Usage

```js
// Import UXCam.
import UXCam from 'react-native-ux-cam';

// Initialize using your app key.
UXCam.startWithKey(key);
```

## History
This is an updated way of integrating the UXCam SDK react-native following on from the original work by Mark Miyashita (https://github.com/negativetwelve) without whom this would have all been much harder!
