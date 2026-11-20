# Order Desk app releases

Android APKs of **Order Desk** retailer app. This repository holds no source
code: each version is a [release](../../releases) with the APK attached as
`orderdesk.apk`.

## Download link used by the app

Admin dashboard → **App settings** → **Download link** (set once):

```
https://github.com/shaharsh624/order-desk-app-client-releases/releases/latest/download/orderdesk.apk
```

It always points to the newest release. The app downloads it in the
background, checks it is a newer build of Order Desk, and shows **Install**.

## Publishing a version

From the app repository (`order-desk-app-client`), on an up-to-date `main`
with `version:` raised in `pubspec.yaml`:

```bash
scripts/release-prod.sh "What changed"
```

The script checks everything first, builds the signed and obfuscated APK,
copies it to this folder (`apks/orderdesk-<version>.apk`), creates release
`v<version>` here with the APK as `orderdesk.apk`, and downloads it back
through the link above to compare. Then set **Latest version** in the admin
App settings.

Always keep the asset name `orderdesk.apk`, or the link above stops working.

## This folder on the development computer

Cloned beside the app repository, as `../order-desk-app-client-releases`.
`apks/` keeps a local copy of every released APK; APKs are never committed
(see `.gitignore`), because GitHub stores them as release assets.
