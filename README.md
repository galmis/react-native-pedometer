# react-native-pedometer

React Native pedometer support for iOS version 8.0 and higher. The module is CMPedometer wrapper. More info about CMPedometer can be found in https://developer.apple.com/library/ios/documentation/CoreMotion/Reference/CMPedometer_class/

## Installation

First install the npm package from your app directory:

```javascript
npm install react-native-pedometer --save
```

### Installation on iOS

In XCode, right click **Libraries**.
Click **Add Files to "[Your project]"**.
Navigate to **node_modules/react-native-sound**.
Add the file **RNPedometer.xcodeproj**.

In the *Project Navigator*, select your project.
Click the build target.
Click **Build Phases**.
Expand **Link Binary With Libraries**.
Click the plus button and add **libRNPedometer.a** under **Workspace**.

Run your project (⌘+R).

## Basic usage

```js
// Import the react-native-pedometer module
var Pedometer = require('react-native-pedometer');

// start tracking from current time
var now = new Date();
Pedometer.startPedometerUpdatesFromDate(now, (pedometerData) => {
  // do something with pedometer data
});

// query pedometer data from selected date to other selected date
var startDate = new Date();
startDate.setHours(0,0,0,0);
var endDate = new Date();
Pedometer.queryPedometerUpdatesBetweenDates(startDate, endDate, (pedometerData) => {
  // do something with pedometer data
});

// determine pedometer availability
Pedometer.isStepCountingAvailable(function(error, isAvailable) {
// do something
});

Pedometer.isDistanceAvailable(function(error, isAvailable) {
// do something
});

Pedometer.isFloorCountingAvailable(function(error, isAvailable) {
// do something
});

Pedometer.isPaceAvailable(function(error, isAvailable) {
// do something
});

Pedometer.isCadenceAvailable(function(error, isAvailable) {
// do something
});

// stop pedometer updates
Pedometer.stopPedometerUpdates();
```

## Notes
- CMPedometer is supported on iPhone 5s and newer.
- Android is not supported.
