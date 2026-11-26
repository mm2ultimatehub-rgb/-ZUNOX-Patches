# ZUNOX YouTube Music profile — 9.30.53

Target supplied by the user. This file records the intended patching and validation steps; it is not a completed APK.

## Input
- App/version: YouTube Music 9.30.53 (versionCode 93053240)
- Original package: `com.google.android.apps.youtube.music`
- Input: APKM containing base and configuration splits
- Install type: standard, non-root

## Intended ZUNOX identity
- Package: `com.zunox.music`
- App label: `ZUNOX Music`
- Must install alongside the original app.

## Patch source
Use the ReVanced patch source explicitly supplied by the user:
`https://gitlab.com/ReVanced/revanced-patches.git`

Do not substitute Morphe patches for this request. The GitHub Actions workflow clones the ReVanced GitLab mirror and prints the source commit SHA used.

## Required patching sequence
1. Confirm the compiled ReVanced bundle contains patches compatible with this exact YouTube Music version.
2. Use a compatible ReVanced CLI and its supported APKM/split workflow. Do not assume the base APK alone is sufficient.
3. Apply the supported package-name/clone patch to set `com.zunox.music`.
4. Apply compatible GmsCore/MicroG support for a non-root install, if available for this app version.
5. Apply custom branding as `ZUNOX Music`; use the actual ZUNOX icon asset supplied by the user, not a placeholder.
6. Inspect final manifest package, authorities, permissions, and split relationships.
7. Sign with the ZUNOX release keystore and verify signature continuity for future updates.

## Acceptance checks
- Installs beside the original YouTube Music.
- No Android package or provider-authority conflict.
- Launch and supported sign-in work.
- Playback and background playback work.
- Release signing and version metadata are correct.

A patch-bundle build alone is not an APK. Do not announce a release until the APK is built, signed, and install-tested.
