# ZUNOX Patches

ZUNOX is an independently branded patching project. The build workflow now uses the **ReVanced patch repository on GitLab**, the exact source URL supplied by the user:

https://gitlab.com/ReVanced/revanced-patches.git

ReVanced's own repository-status notice identifies this GitLab mirror as its current development location while its GitHub repository is unavailable. Each workflow run clones this source and prints the exact upstream commit SHA.

## YouTube Music target profile

- Input APKM: YouTube Music 9.30.53 (versionCode 93053240), previously supplied by the user
- Original package: `com.google.android.apps.youtube.music`
- Intended clone package: `com.zunox.music`
- Intended app label: `ZUNOX Music`
- Install mode: non-root, alongside the original app

The profile is a build plan, not a finished patched APK.

## Workflow output

GitHub Actions clones the ReVanced GitLab source and runs its Gradle build. A successful run uploads the compiled `.rvp` patch bundle as the `zunox-revanced-patches` artifact for 14 days.

**Important:** compiling the patch bundle does not patch the APKM or create a signed APK. The APK must still be patched using the compatible ReVanced CLI, with split APK handling, package/manifest validation, ZUNOX release signing, and installation testing.

## Release acceptance

Do not call an APK ready until:
1. The supplied APKM's base and configuration splits are handled correctly.
2. ReVanced patches compatible with this exact app version are applied.
3. The final manifest package is verified as `com.zunox.music`.
4. The APK is signed with the ZUNOX release key.
5. It installs alongside the original app and passes launch/playback checks.

## License

ReVanced Patches is GPLv3. Preserve license/notice files, record modifications, and provide corresponding source and build instructions for derivative distributions.
