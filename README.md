# Team Attendance Android project

This project packages the included `index.html` into an Android app using Capacitor.

## Build the APK with GitHub Actions

1. Create a GitHub repository.
2. Upload the **contents** of this folder (not the ZIP itself) to the repository root.
3. Open the **Actions** tab.
4. Select **Build Android APK** and click **Run workflow** (or wait for the workflow triggered by a push).
5. When the run succeeds, download the `Team-Attendance-APK` artifact.
6. Extract the downloaded artifact ZIP to get `app-debug.apk`.

The workflow generates the Android platform during the build, so you do not need to commit an `android/` folder.

## Important

The included app currently stores its data in the browser's local storage on that device. This is suitable for a prototype, but it does not automatically synchronize attendance data between different employees' phones.
