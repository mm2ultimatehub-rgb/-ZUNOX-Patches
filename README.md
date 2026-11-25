# ZUNOX Patches

ZUNOX is an independently branded patch project built from the Morphe Patches source tree.

## Source and attribution

- Upstream source: https://github.com/MorpheApp/morphe-patches
- Upstream revision pinned in this repository: `c4818af779bab85505e5e9169d0789b422bb99cd`
- Upstream project identifies its patches as based on prior ReVanced work.
- This repository does not claim to be the Morphe project and does not use Morphe branding.

The upstream source is tracked as a Git submodule at `upstream/morphe-patches`. Initialize it with:

```sh
git clone --recurse-submodules https://github.com/mm2ultimatehub-rgb/-ZUNOX-Patches.git
```

If already cloned:

```sh
git submodule update --init --recursive
```

## YouTube Music compatibility

The upstream README at the pinned revision lists YouTube Music **9.30.53** among its supported versions. This is an upstream compatibility declaration only; ZUNOX has not yet built or tested a patched APK against the supplied APKM. Compatibility must be verified by building and testing.

## ZUNOX development status

- [x] Connect and pin the upstream Morphe patch source.
- [x] Preserve upstream license and NOTICE files in this repository.
- [ ] Review upstream patcher/library versions and build prerequisites.
- [ ] Add ZUNOX-specific branding/configuration as a clearly marked derivative.
- [ ] Build the patch bundle and test against YouTube Music 9.30.53.
- [ ] Publish a verified release only after successful build and install tests.

## License and notices

The upstream project is licensed under GNU GPL v3 with additional requirements under GPLv3 Sections 7(b), 7(c), and 7(e). The upstream LICENSE and NOTICE are retained in this repository. Derivative versions must be clearly marked as modified, preserve the NOTICE, and must not imply Morphe endorsement or use its trademarks/logos without permission.

No compiled patch bundle or APK is included at this stage.
