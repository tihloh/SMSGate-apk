# SMSGate Android APK

Public Android download repository for **SMSGate**.

## Download

- **[Latest signed SMSGate APK](https://github.com/tihloh/SMSGate-apk/releases/latest/download/SMSGate.apk)** — becomes available when the first versioned signed build is published.
- [Existing v0.3.16 development/debug APK](https://github.com/tihloh/SMSGate-apk/releases/download/debug-5-1/SMSGate-debug.apk) — older debug build; cannot reliably update in place.
- [All releases](https://github.com/tihloh/SMSGate-apk/releases)

## Auto-updates

SMSGate checks this repository's GitHub Releases for versioned releases, such as `v0.3.17.8`, that contain `SMSGate.apk`. The app verifies its application ID, signing certificate, and increasing Android versionCode before starting an Android PackageInstaller session. Android may still require the user to approve installation.

Only APKs signed with the **same persistent certificate** can update an installed SMSGate copy in place. The old debug APK was built using a temporary signing key. Switching from that build to the signed release channel may require a one-time uninstall; uninstalling can erase app settings and queued data. Back up or reconcile pending gateway work before doing that.

Signed publication from the private source repo is enabled when all four signing secrets (`ANDROID_KEYSTORE_BASE64`, `ANDROID_KEYSTORE_PASSWORD`, `ANDROID_KEY_ALIAS`, `ANDROID_KEY_PASSWORD`) and the `SMSGATE_APK_PUSH_TOKEN` are available. Debug APKs remain in the private repository's GitHub Actions artifacts.

These are sideloaded development builds, not Google Play-approved or production-certified releases. SMS permission eligibility and real-device carrier testing are separate requirements.
