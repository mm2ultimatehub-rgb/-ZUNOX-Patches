# ZUNOX YouTube Music profile — 9.30.53

This is the intended patch configuration for the supplied YouTube Music 9.30.53 APKM. It is a configuration specification, not a compiled patch bundle or APK.

## Input
- Application ID: `com.google.android.apps.youtube.music`
- Version: `9.30.53` (versionCode `93053240`)
- Input format: APKM split package (base APK plus configuration splits)
- Target install type: standard, non-root installation

## Required package/clone settings
1. Select **Clone app**.
2. Set **Package name** to `com.zunox.music` (not Default).
3. Keep **Update permissions** and **Update providers** enabled in the UI unless the patch implementation overrides them. In the pinned upstream source, YouTube Music is explicitly handled by the **GmsCore support** patch for permission/provider rewriting; Clone app itself skips those two rewrites for this package.
4. Select **GmsCore support**. The pinned upstream implementation depends on Clone app, rewrites the app package and Google service references, and marks this patch unavailable for root-mounted installs.
5. For branding, select **Custom branding** and set app name to `ZUNOX Music`; supply the ZUNOX icon asset when the patcher requests one.

## Why both package-related patches matter
The pinned upstream implementation defines Clone app as the patch that changes the manifest package name. The YouTube Music GmsCore support patch depends on Clone app and updates Google service references, permissions, authorities, and provider integration for a non-root cloned install. For YouTube Music, the upstream Clone app code intentionally leaves permission/provider rewriting to GmsCore support.

## Validation required before release
- Build the patch bundle from the pinned upstream source.
- Patch all required APK splits consistently; do not treat this APKM as a single standalone APK.
- Verify the final manifest package is exactly `com.zunox.music`.
- Verify no install-time permission/provider authority collisions remain.
- Sign the output with the ZUNOX release key.
- Install beside the original YouTube Music and test launch, sign-in, playback, background playback, downloads/sharing and update behavior.

## Current status
The profile has been documented in ZUNOX. No patch bundle has been compiled, no APK has been produced or signed, and no install test has passed yet. Do not distribute this profile as a finished APK.
