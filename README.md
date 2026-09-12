# LineageOS 19.1 For Exynos 7870

Official device manifests and common trees for building LineageOS 19.1 (Android 12L) on Samsung Exynos 7870 devices.

---

## Supported Devices

| Codename | Device |
| :--- | :--- |
| `j7xelte` | Samsung Galaxy J7 (2016) |
| `j7改进` -> `j7velte` | Samsung Galaxy J7 Core / Nxt / Neo (2017) |
| `j7y17lte` | Samsung Galaxy J7 Pro (2017) |
| `on7xreflte` | Samsung Galaxy J7 Prime 2 / On7 Prime (2018) |
| `a3y17lte` | Samsung Galaxy A3 (2017) |
| `j6lte` | Samsung Galaxy J6 (2018) |
| `j5y17lte` | Samsung Galaxy J5 Pro (2017) |
| `on7xelte` | Samsung Galaxy J7 Prime / On7 (2016) |

---

## How to Build

### 1. Initialize LineageOS 19.1 Source
```bash
mkdir android-src && cd android-src
repo init -u https://github.com/LineageOS/android.git -b lineage-19.1 --git-lfs
```

### 2. Add Local Manifests

#### Option A: Sync All Devices (Master Manifest)
```bash
git clone https://github.com/Exynos7870-Revived-Beta/android_manifest_samsung_universal7870-common.git -b lineage-19.1 .repo/local_manifests
```
*(Keep `7870.xml` and remove individual device XMLs if you want to sync all trees simultaneously).*

#### Option B: Single Device Build
```bash
mkdir -p .repo/local_manifests
curl -sL https://raw.githubusercontent.com/Exynos7870-Revived-Beta/android_manifest_samsung_universal7870-common/lineage-19.1/<device>.xml > .repo/local_manifests/<device>.xml
```
*(Replace `<device>` with your target codename, e.g. `j6lte`)*

### 3. Sync Repositories
```bash
repo sync -c --no-clone-bundle --no-tags --optimized-fetch --prune -j16
```

### 4. Apply Platform Patches
If required for your source tree, apply the patches from the `patches/` directory using:
```bash
bash patches/apply_patches.sh
```

### 5. Build
```bash
source build/envsetup.sh
lunch lineage_<device>-userdebug
m bacon -j16
```

---

## Credits
- @Astrako
- @FlominatorGD
- @Batuhantrkgl
- Exynos7870 Community
