# trackee-clone
This app is supposed to send real-time location co-ords to pubnub dashboard


WHAT IS HAPPENING UPTIL NOW?

- App is running on device
- Picking my co-ords (they were hard coded, that's why)
- Showing pointer on the co-ordinates

WHAT IS NOT HAPPENING AND NEEDS TO HAPPEN?

- Move pointer as the location changes
- Update location co-ordinates on the PubNub dashboard 
- Real-time data push-ing to PubNub 
  (for now nothing is being pushed to db as the app is not detecting location changes. Once it does that it is expected to auto-push the coords)
  
 REACT NATIVE SETUP ON PHYSICAL DEVICE
 
 - Have phone in developer mode 
        - go to Settings > about phone > build Number (tap 7 times)
        - Developer options will appear in settings menu. Turn USB DEBUGGING on.
        - Connect phone through cable to laptop
 - Open cmd and write 'adb devices'. This will show your phone if connected
 - Write 'adb reverse tcp:8081 tcp:8081' in cmd. This will enable hearing on port
 
 RUNNING PROJECT
 - npm install
 - react-native run-android
 
 Errors that can show up:
 
 1. unable to load script from assets 'index.android.bundle'

mkdir android\app\src\main\assets

react-native bundle --platform android --dev false --entry-file index.js --bundle-output android\app\src\main\assets\index.android.bundle --assets-dest android\app\src\main\res

{  

            (if this causes regular expression error: or Invalid regular expression: /(.*\\__fixtures__\\.*|node_modules[\\\]react[\\\]dist[\\\].*|website\\node_modules\\.*|heapCapture\\bundle\.js|.*\\__tests__\\.*)$/: Unterminated character class. Run CLI with --verbose flag for more details.)


             try:

            {project_root}\node_modules\metro-config\src\defaults\blacklist.js

          change blacklist variable to: var sharedBlacklist = [
          /node_modules[\/\\]react[\/\\]dist[\/\\].*/,
          /website\/node_modules\/.*/,
          /heapCapture\/bundle\.js/,
          /.*\/__tests__\/.*/ ];
}

react-native run-android

2. Error: Command failed: gradlew.bat app:installDebug
cd android
gradlew.bat installDebug
cd ..
react-native run-android
