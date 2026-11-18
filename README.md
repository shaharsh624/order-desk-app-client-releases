# The M Zone app releases

Android APKs of **The M Zone** retailer app. This repository holds no source
code: each version is a [release](../../releases) with the APK attached as
`themzone.apk`.

## Download link used by the app

Admin dashboard → **App settings** → **Download link**:

```
https://github.com/shaharsh624/the-m-zone-app-client-releases/releases/latest/download/themzone.apk
```

It always points to the newest release. The app downloads it in the
background, checks it is a newer build of The M Zone, and shows **Install**.

## Publishing a version

1. In the app repository: raise `version:` in `pubspec.yaml`, then run
   `scripts/build-release.sh` (signed with the release key).
2. Create a release here with the APK named `themzone.apk`:

   ```bash
   gh release create v1.0.1 build/app/outputs/flutter-apk/app-arm64-v8a-prod-release.apk#themzone.apk \
     --repo shaharsh624/the-m-zone-app-client-releases --title "1.0.1"
   ```

3. Admin → **App settings** → set **Latest version** to the same version.

Always keep the file name `themzone.apk`, or the link above stops working.
