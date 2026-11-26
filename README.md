# ZUNOX Patches

ZUNOX is an independently branded patching project. CI builds the ReVanced patch source from the GitLab repository specified by the project owner:

https://gitlab.com/ReVanced/revanced-patches.git

Each build records the exact upstream commit SHA in the package.

## Required CI secret

The ReVanced Gradle plugin is hosted in GitHub Packages. Add these repository secrets before running the workflow:

- `REVANCED_PACKAGES_TOKEN`: a GitHub token with `read:packages` access and permission to download the ReVanced Gradle plugin package.
- `REVANCED_PACKAGES_USERNAME` (optional): the GitHub account username that owns the token. If omitted, the workflow uses the workflow actor's username.

Do not commit tokens or place them in source files. The workflow intentionally stops with a clear error if the token is missing.

## YouTube Music target profile

- Input APKM: YouTube Music 9.30.53 (versionCode 93053240), previously supplied by the user
- Original package: `com.google.android.apps.youtube.music`
- Intended clone package: `com.zunox.music`
- Intended app label: `ZUNOX Music`
- Install mode: non-root, alongside the original app

The profile is a specification only. It is not a compiled ZUNOX patch, patched APK, or signed installer.

## Workflow output

A successful GitHub Actions run uploads the `zunox-patch-package` artifact (ZIP plus the upstream `.rvp` bundle) for 14 days. The workflow validates the RVP and ZIP archives and prints a SHA-256 checksum.

**This workflow does not yet produce an APK.** The compiled upstream RVP must still be applied to the user's original APKM using a compatible ReVanced CLI. A separately authored ZUNOX patch RVP, logo asset, split APK handling, package/manifest validation, release signing, and install/playback tests remain required before an APK can be called complete.

## Release acceptance checklist

Do not label an APK ready until:
1. The supplied APKM base and configuration splits are processed correctly.
2. The patches are compatible with the exact target app version.
3. Any ZUNOX-owned patches are independently compiled and documented.
4. The final manifest package is verified as `com.zunox.music`, including provider authorities.
5. The actual ZUNOX logo is included; no placeholder is used.
6. The APK is signed with the ZUNOX release key.
7. It installs alongside the original app and passes launch/playback checks.

## License

ReVanced Patches is GPLv3. Preserve upstream notices, record modifications, and provide corresponding source and build instructions for derivative distributions.
