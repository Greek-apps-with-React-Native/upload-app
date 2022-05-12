# How to upload a React Native app to Google Play Console and Apple Store Connect.
Instructions on how to upload a React Native app.


#### To create a bundle for google play

- **FIRST**: Check the changes and fill in the `InfoScreen`.
- change version number i.e. go to `android/app/build.gradle`.
  - versionCode 1 // Change to a higher number
  - versionName "1.0.1" // Change to a higher number
- `cd android && ./gradlew bundleRelease` // For generating abb for google play. Or,
- `cd android && ./gradlew assembleRelease` // for apk files, for direct instalation.
- to test it, `cd .. && npx react-native run-android --variant=release`
- go to `Google Play Console -> Create new Release`. Choose file from `android/app/build/outputs/bundle/release/app-release.aab `, full in the info, then save, then roll out new release.
- upload an other release to closed testing, so users will be notified with new versions.
- Don't forget to check the Inbox for pre-launch report.
- check also this [post](https://stackoverflow.com/questions/66911642/google-play-android-app-internal-testing-update-button-not-shown-to-internal-t) to get the update button in Google Play when new release is uploaded.

#### To create a bundle for App Store

- Increase `Build` number in xcode.
- choose as device: `Any iOS Device arm64`.
- Got to `Product => Archive` and make an archive.
- Go to apple connect store:
- Click `apps => TestFlight => Manage` (at the last build).
- Check both with `yes` in the dialog modal.
- Click on the `build` number. This brings up a page with `Groups` on it.
- Click on the `plus symbol` next to the `Group (0)`. Add an external group.
- Follow submission prompts.
- Now the app is waiting for testing.
- check [video](https://www.youtube.com/watch?v=DLvdZtTAJrE&t=84s)
