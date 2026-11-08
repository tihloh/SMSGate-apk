# SMSGate Android APK

Public Android distribution repository for **stable, signed SMSGate releases only**.

## Stable download

- [Latest stable APK](https://github.com/tihloh/SMSGate-apk/releases/latest/download/SMSGate.apk) — available only after the first signed stable release is published.
- [Stable release history](https://github.com/tihloh/SMSGate-apk/releases) — stable releases use version tags such as `v0.3.17.11` and contain `SMSGate.apk`.

**No debug preview APKs will be published going forward.** Historical `debug-*` builds are development prereleases, not supported by the in-app updater. Do not use them for production installs.

## In-app updates

SMSGate checks GitHub Releases for a stable version tag (`vMAJOR.MINOR.PATCH.BUILD`) with an asset named `SMSGate.apk`. Android verifies that the new APK has a greater versionCode, the same package ID, and the **same signing certificate** as the installed app.

Every stable release must be signed using one **persistent, securely backed-up Android release keystore**. Never generate a new signing key on each build. A debug-signed installation cannot normally be updated in place to the stable signing certificate. Switching from a debug installation may require a one-time uninstall/reinstall, which can erase locally saved server tokens, pairing settings and unsent SMS work. Resolve pending SMS work and retain a fresh pairing QR before switching.

## Release signing setup

Stable distribution from the private `tihloh/SMSGate` source repository requires these GitHub Actions secrets:

- `ANDROID_KEYSTORE_BASE64`: base64 of the **same** long-lived Android release keystore for all versions.
- `ANDROID_KEYSTORE_PASSWORD`: password protecting that keystore.
- `ANDROID_KEY_ALIAS`: signing key alias inside that keystore.
- `ANDROID_KEY_PASSWORD`: signing key password.
- `SMSGATE_APK_PUSH_TOKEN`: GitHub token with permission to publish releases to this repository.

Configure the secrets in the private source repository under **Settings → Secrets and variables → Actions**. Store the original keystore and passwords in a secure offline backup. Do not commit or share signing keys, secret values, or release credentials in source files or issues.

The private workflow tests Android code, verifies release-signing secrets, builds and verifies a signed release APK, and publishes `SMSGate.apk` to a versioned stable GitHub Release. If the persistent signing secrets are missing, it **fails without publishing anything**; it never falls back to a debug preview.

These releases are sideloaded Android packages, not a claim of Google Play approval or production certification. SMS permission eligibility and real-device carrier testing remain separate requirements.
