microG/UnifiedNlp Installer
===

**Flashable ZIP** to install [microG](https://microg.org) or [UnifiedNlp](https://github.com/microg/android_packages_apps_UnifiedNlp/blob/master/README.md) into an Android system. This also includes an OTA survival `addon.d` script.  
You'll usually install them normally, but Google blocked userspace location providers in Android 7+, and some ROMs have not applied [required patches](https://github.com/microg/android_packages_apps_UnifiedNlp/tree/master/patches) yet, like LineageOS.

**microG** is a free-as-in-freedom re-implementation of [Google’s proprietary Android user space apps and libraries](https://arstechnica.com/gadgets/2013/10/googles-iron-grip-on-android-controlling-open-source-by-any-means-necessary/).  
**Unified Network Location Provider** (UnifiedNlp) is a library that provides Wi-Fi- and Cell-tower-based geolocation [with configurable plugins](https://github.com/microg/android_packages_apps_UnifiedNlp#usage) to applications that use Google’s network location provider. It is included in GmsCore but can also run independently on most Android systems.


Install
===

You'll need a custom recovery installed on your device, such as [TWRP](https://twrp.me/).

Restart your device into recovery and start `ADB sideload`. Then run:
```
adb sideload <flashable-zip-name>
```

Alternatively, copy the resulting ZIP to your device storage, restart your device into recovery and use the GUI `Install` or `Install ZIP` option.


Build
===

### Requirements

[XMLStarlet](http://xmlstar.sourceforge.net/download.php) is needed to parse F-Droid-like repo indexes.

On Debian/Ubuntu systems, run `sudo apt install xmlstarlet`

### Build ZIP

Run the `build-zip.sh` shell script:
```
source build-zip.sh
```

This will generate a `microg_YYYY-MM-DD.zip` file.

### ZIP Flavours

You can **add you own flavour** just by writing a `<newflavour>_config.txt` file.

`build-zip.sh` accepts a single `<flavour>` string argument. Each flavour has a `<flavour>_config.txt` file.
```
source build-zip.sh <flavour>
```

This will generate a `<flavour>_YYYY-MM-DD.zip` file.

For example, to build the `unifiednlp` flavour, run:
```
source build-zip.sh unifiednlp
```

This will generate a `unifiednlp_YYYY-MM-DD.zip` file.
