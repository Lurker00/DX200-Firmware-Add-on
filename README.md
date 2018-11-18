# iBasso DX200 firmware add-on by Lurker

## Introduction
Android 8.1 for DX200 protects main partitions with [Verity](https://source.android.com/security/verifiedboot), which makes it tricky for end user to flash custom firmware. [Magisk](https://magiskmanager.com/) allows developers to alter system systemless-ly, i.e. without any direct modification of the protected parts of the firmware image. That's why my modifications for 8.1 are distributed as add-ons: you must have installed and running the original firmware, then you apply (flash over) an add-on. It makes the download smaller, update process faster, and *it is compatible between different official firmware builds*!

The only current drawback is that Windows-only tool is required to flash an add-on, but, on the other hand, the same tool is required to flash the official firmware.

To check the current add-on version in Android mode, go to _Settings_, _About DX200_, _Build number_ at the bottom.

**WARNING:** Add-ons are *not* compatible with encrypted devices!

## How to apply or update the add-on
The ZIP archive with add-on contains `readme.txt` file with full instruction. Please read and follow it.

**Note:** Updating an add-on removes additional [Magisk](https://magiskmanager.com/) modules. You'll have to re-install them after the update.

## Changes made
### Android
* Google Play Store added.
* The process of [device registration](https://www.google.com/android/uncertified/) is much simplified (required to make Google Play Services work on uncertified device).
* [Magisk](https://magiskmanager.com/) can be used to install additional modules, and to provide root access.
* [USB Audio application](https://github.com/Lurker00/DX200-USB-Audio-Release/blob/master/README.md), which is also useful for its [System settings](https://github.com/Lurker00/DX200-USB-Audio-Release/blob/master/README.md#system-settings).
* Custom build of [HibyMusic](https://play.google.com/store/apps/details?id=com.hiby.music), which plays bit perfect PCM up to 32/384kHz with no additional efforts, and fully compatible with [USB Audio application](https://github.com/Lurker00/DX200-USB-Audio-Release/blob/master/README.md) for bitperfect DSD and SACD ISO playback.
* 126MHz CPU frequency added (216MHz is officially lowest), which is enough for most tasks.
### Mango
* Removed Android services, that are not used in this mode.
* Performance insreased.
### Common
* SD-card read/write speed increased.
* Safer parameters of battery charger to prevent overheating.
* Safer parameters for CPU, GPU, RAM.

## History of public releases
**1.12**:
* Full support for [USB Audio application](https://github.com/Lurker00/DX200-USB-Audio-Release/blob/master/README.md).
* Custom build of [HibyMusic](https://play.google.com/store/apps/details?id=com.hiby.music) included.
* Fix: full label is shown for exFAT formatted SD-cards.

**1.10** - Increased SD-card read/write speed, optimized Mango mode.

**1.09** - first public release.

