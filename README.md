# LineageOS-18.1 For Exynos7870

### How to build ###

```bash
# Create dirs
$ mkdir LineageOS-18.1 && cd LineageOS-18.1

# Init repo
$ repo init -u https://github.com/LineageOS/android.git -b lineage-18.1 --git-lfs

# Clone my local repo
$ git clone https://github.com/Exynos7870-Revived-Beta/android_manifest_samsung_universal7870-common.git -b lineage-18.1-oss_bsp-vndk .repo/local_manifests

# Sync
$ repo sync --no-repo-verify -c --force-sync --no-clone-bundle --no-tags --optimized-fetch --prune -j`nproc` -v

# Build
$ . build/envsetup.sh && lunch lineage_DEVICECODENAME-userdebug
```

## Credits
2021 @Astrako 
2022 @FlominatorGD
2025 @Batuhantrkgl

## Contact
Telegram support group: <s>https://t.me/batuhan_s_buildsv2</s>
