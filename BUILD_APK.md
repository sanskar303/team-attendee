# Building the Team Attendee APK

The APK has to be compiled with the Android SDK, so it is built from this project rather than included in the zip.

## Option A — GitHub (no installs)
1. Create a GitHub repository and upload everything in this folder.
2. Open **Actions → Build Android APK → Run workflow**.
3. When it finishes, download **team-attendee-debug-apk** from the run page. Unzip it to get `app-debug.apk`, copy it to your phone and install it (allow "install unknown apps").

## Option B — On your computer
Requirements: Node 18+, JDK 17, Android Studio (or the Android SDK command-line tools).
```
npm install
npx cap add android
npx cap sync android
cd android && ./gradlew assembleDebug      # Windows: gradlew.bat assembleDebug
```
APK: `android/app/build/outputs/apk/debug/app-debug.apk`
Or run `npx cap open android` and use *Build → Build APK(s)* in Android Studio.

## Option C — Install as an app right now (no APK)
Host the `www` folder on any HTTPS site (Netlify / GitHub Pages / Vercel), open it in Chrome on Android, and choose **Add to Home screen → Install**.

## Release build
The debug APK is for testing. For Play Store, create a keystore and build `assembleRelease` / an AAB in Android Studio.
