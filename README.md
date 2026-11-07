# SMSGate Android APK

Public Android download repository for **SMSGate**.

## Download

- **[Latest signed SMSGate APK](https://github.com/tihloh/SMSGate-apk/releases/latest/download/SMSGate.apk)** — becomes available when the first versioned signed build is published.
- **[Latest updater-enabled debug APK](https://github.com/tihloh/SMSGate-apk/releases/latest/download/SMSGate-debug.apk)** — development preview. A newer release will provide the Check for app updates button.
- [Older v0.3.16 debug APK](https://github.com/tihloh/SMSGate-apk/releases/download/debug-5-1/SMSGate-debug.apk) — does not contain the update checker.
- [All releases](https://github.com/tihloh/SMSGate-apk/releases)

## Auto-updates

SMSGate checks this repository's GitHub Releases for versioned releases, such as `v0.3.17.8`, that contain `SMSGate.apk`. The app verifies its application ID, signing certificate, and increasing Android versionCode before starting an Android PackageInstaller session. Android may still require the user to approve installation.

Only APKs signed with the **same persistent certificate** can update an installed SMSGate copy in place. **Debug APKs use temporary signing keys**, so installing the latest debug preview over an existing debug installation may also fail. They show the updater interface for testing but cannot support reliable in-place auto-updates. Signed releases are the recommended channel when the persistent keystore is configured. Switching signing certificates may require a one-time uninstall, which can erase app settings and queued data. Back up or reconcile pending gateway work first.

Signed publication from the private source repo is enabled when all four signing secrets (`ANDROID_KEYSTORE_BASE64`, `ANDROID_KEYSTORE_PASSWORD`, `ANDROID_KEY_ALIAS`, `ANDROID_KEY_PASSWORD`) and the `SMSGATE_APK_PUSH_TOKEN` are available. Debug APKs remain in the private repository's GitHub Actions artifacts.

These are sideloaded development builds, not Google Play-approved or production-certified releases. SMS permission eligibility and real-device carrier testing are separate requirements.
