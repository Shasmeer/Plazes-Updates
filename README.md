# Plazes public UAT distribution

This repository is **only** for public Android UAT binaries and update metadata. The private source code remains in `Shasmeer/Plazes`.

## Release contract
Create a GitHub Release with a unique increasing version tag (e.g. `v0.7.0-uat`) and attach the APK as `Plazes-UAT.apk`. Never publish source code, secrets, private photos, or signing keys here.

An in-app updater should query `https://api.github.com/repos/Shasmeer/Plazes-Updates/releases/latest`, compare the installed Android `versionCode` against a trusted numeric version in release metadata, and download the APK asset over HTTPS. Android must prompt the user to approve installation. The APK must use the **same application ID and signing certificate** as the installed app and a higher versionCode.

## Important
A GitHub Actions artifact is not a public release asset. Publishing from the private source repository to this public repository requires a narrowly scoped credential with Contents write access to this public repository, stored as a GitHub Actions secret in the private source repository. Do not paste credentials into issues, files, or chat.

Do not publish an APK until its signing certificate continuity and install-over-existing-app behavior are verified on a device.
