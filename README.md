# SMSGate Android APK

Public download repository for the Android builds of **SMSGate**.

## Download

**[Latest SMSGate APK](https://github.com/tihloh/SMSGate-apk/releases/latest/download/SMSGate-debug.apk)**

Browse the [release history](https://github.com/tihloh/SMSGate-apk/releases) for older APKs.

The latest-download link becomes available when the first build is published.

## About these builds

These are **development/debug builds**, produced automatically from the private SMSGate source repository after Android compilation and unit tests succeed. They are **not production-certified or Google Play-approved releases**.

Android may require you to allow installation from your browser or file manager. Only install APKs you trust.

**Updates and signing:** Android only installs an APK over an existing installation when the package ID and signing certificate match and the versionCode is not lower. A GitHub Actions debug build may be signed with an ephemeral debug key on each runner unless a persistent signing key is configured. In that case, uninstalling the previous installation could be required, and uninstalling can erase local app data. For reliable in-place updates, configure persistent signing in the private build workflow and increment the Android versionCode appropriately.

## Source and publishing

The source repository is private. Successful builds from its `main` branch can publish an APK as a GitHub Release in this repository. Releasing requires a GitHub Actions secret granting narrowly scoped write access to this repository.
