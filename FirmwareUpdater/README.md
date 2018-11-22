# Firmware update from SD-card

RockChip SoC based devices support firmware updates by booting from a specially prepared SD-card. The official way requires a Windows-based application from RockChip and device boot loader file.

[`DX200FirmwareUpdater.zip`](https://github.com/Lurker00/DX200-Firmware-Add-on/releases/download/v1.12/DX200-A8.1-L1.12-sdupdate.zip) archive contains ready to use SD-card image file with 4GB partition, to update firmware on iBasso DX200.

## Prepare bootable SD-card
You may use any SD-card with capacity of 4GB or more.

**WARNING:** writing the SD-card image file erases all the data on the card! To restore the SD-card for normal use, please use [SD Memory Card Formatter](https://www.sdcard.org/downloads/formatter_4/), available for MacOS and Windows.

You need to unzip the downloaded archive and write the `.img` file directly to SD-card. Under Windows, [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/) can be used. Under Linux and MacOS, [`dd` command](https://en.wikipedia.org/wiki/Dd_(Unix)) from console performs the task, though great caution is required! Also, there is [Etcher](https://en.wikipedia.org/wiki/Etcher_(software)) GUI application that may do it (I'm not sure!).

If all went right way, you should have the following files in the root folder of the SD-card:
* `sd_boot_config.config`
* `sdupdate.img`
* `rksdfw.tag`

`sdupdate.img` is empty (0 bytes), and it is the placeholder for the real firmware update image file.

## Update firmware

You need firmware update image file. For Android Oreo, iBasso provides `update.img` in its download. My firmware releases, to be used with RockChip FactoryTool (*not* files to be used with rkflashtool!), contain compatible `.img` file as well.

1. Rename required `.img` file to `sdupdate.img`.
2. Copy resulting `sdupdate.img` to the prepared bootable SD-card, confirming overwriting existing file.
3. Safely remove (unmount) SD-card from the computer.
4. Turn DX200 off.
5. Insert SD-card into DX200.
6. Turn DX200 on.

In a few seconds it should start updating the firmware. At the end, it will prompt you to remove the SD-card from the slot, and will continue update, and then boot the device.

## Useful notes

You may keep several firmware images on the bootable SD-card under different file names. Only the one named `sdupdate.img` is used for the firmware update.

You may use this SD-card to revert back from Android 8.1 to 2.10.215-L0 using [full flash firmware image](https://github.com/Lurker00/DX200-firmware/releases/download/v2.10.215/DX200FirmwareV2.10.215-L0-fullflash.zip).

