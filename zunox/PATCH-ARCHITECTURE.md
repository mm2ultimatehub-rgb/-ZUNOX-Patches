# ZUNOX patch architecture

This repository must not mislabel an upstream ReVanced bundle as a finished custom ZUNOX patch bundle.

## Separate responsibilities

1. **Upstream patch engine:** build ReVanced patches from the user's specified GitLab source and record the exact commit.
2. **ZUNOX profile:** `zunox/profile.json` declares the target app/version, clone package, branding and validation contract.
3. **ZUNOX-owned code:** future Kotlin patches stay isolated and compile against the exact upstream API. Do not rename upstream code and call it original.
4. **Patch application:** combine upstream RVP with any separately compiled ZUNOX RVP through the CLI's supported multiple-bundle inputs. Branding/package options should use real upstream patch options, not invented bytecode patches.
5. **APK release:** split/APKM handling, manifest/provider checks, signing and install/playback tests are distinct from RVP compilation.

## Current status

The workflow builds the upstream `.rvp` and packages it beside the ZUNOX profile. It does not claim a separate ZUNOX Kotlin patch has compiled or an APK has been produced.

## Target identity

- App label: ZUNOX Music
- Clone package: `com.zunox.music`
- Original package: `com.google.android.apps.youtube.music`
- User-provided target: YouTube Music 9.30.53 / 93053240

Use the actual ZUNOX logo asset for the icon; never substitute a placeholder without approval.
