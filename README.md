# iBasso DX200 firmware add-on by Lurker

## Introduction
Android 8.1 for DX200 protects main partitions with [Verity](https://source.android.com/security/verifiedboot), which makes it tricky for end user to flash custom firmware. [Magisk](https://magiskmanager.com/) allows developers to alter system systemless-ly, i.e. without any direct modification of the protected parts of the firmware image. That's why my modifications for 8.1 are distributes as add-ons: you must have installed and running the original firmware, then you apply (flash over) an add-on. It makes the download smaller, update process faster, and there is a chance that an add-on would be compatible between different official firmware builds!

The only current drawback is that Windows-only tool is required to flash an add-on, but, on the other hand, the same tool is required to flash the official firmware.

**WARNING:** Add-ons are not compatible with encrypted devices!

## How to apply
The ZIP archive with add-on contains `readme.txt` file with full instruction. Please read and follow it.

## Changes made
1. Google Play Store added.
2. The process of [device registration](https://www.google.com/android/uncertified/) is much simplified (required to make Google Play Services work on uncertified device).
3. Magisk can be used to install additional modules, and to provide root access.

**Note:** Updating an add-on removes additional Magisk modules. You'll have to re-install them after the update.
