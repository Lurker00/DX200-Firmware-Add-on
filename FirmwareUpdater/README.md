# Firmware update from SD-card

RockChip SoC based devices support firmware updates by booting from a specially prepared SD-card. The official way requires a Windows-based application from RockChip ("Create Upgrade Disk Tool", aka "SD Firmware Tool"), and a suitable device boot loader file. Using them, I've prepared such an SD-card for you.

[`DX200FirmwareUpdater.zip`](https://github.com/Lurker00/DX200-Firmware-Add-on/releases/download/v1.12/DX200FirmwareUpdater.zip) archive contains ready to use SD-card image file with 4GB partition, to update firmware on iBasso DX200.

## Prepare bootable SD-card
You may use any SD-card with capacity of 4GB or more.

**WARNING:** writing the SD-card image file erases all the data on the card! To restore the SD-card for normal use, please use [SD Memory Card Formatter](https://www.sdcard.org/downloads/formatter_4/), available for MacOS and Windows.

You need to unzip the downloaded archive ([`DX200FirmwareUpdater.zip`](https://github.com/Lurker00/DX200-Firmware-Add-on/releases/download/v1.12/DX200FirmwareUpdater.zip)) and write the `DX200FirmwareUpdater.img` file directly to SD-card. Under Windows, [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/) can be used. Under Linux and MacOS, [Etcher](https://en.wikipedia.org/wiki/Etcher_(software)) GUI application performs the task (see [below](#an-instruction-for-macos-users) for example). Experienced users may use [`dd` command](https://en.wikipedia.org/wiki/Dd_(Unix)) from console, though great caution is required!

If all went right way, you should have SD-card labeled as `DX200UPDATE`, with the following content:
* `sd_boot_config.config`
* `sdupdate.img`
* `rksdfw.tag`

`sdupdate.img` is empty (0 bytes), and it is the placeholder for the real firmware update image file.

## Update firmware

**WARNING:** Firmware update from bootable SD card is performed only when DX200 is not connected to a power supply or USB port. Charge it before starting firmware update!

You need firmware update image file. For Android Oreo, iBasso provides `update.img` in its download. My firmware releases, to be used with RockChip FactoryTool (*not* files to be used with rkflashtool!), contain compatible `.img` file as well.

1. Rename required `.img` file to `sdupdate.img`.
2. Copy resulting `sdupdate.img` to the prepared bootable SD-card, confirming to overwrite existing file.
3. Safely remove (unmount) SD-card from the computer.
4. Disconnect DX200 from a charger or USB port (if it is connected).
5. Turn DX200 off.
6. Insert SD-card into DX200.
7. Turn DX200 on.

In a few seconds it should start updating the firmware. At the end, it will prompt you to remove the SD-card from the slot, and will continue update, and then boot the device.

## Useful notes

You may keep several firmware images on the bootable SD-card under different file names. Only the one named `sdupdate.img` is used for the firmware update.

You may use this SD-card to revert back from Android 8.1 to 2.10.215-L0 using [full flash firmware image](https://github.com/Lurker00/DX200-firmware/releases/download/v2.10.215/DX200FirmwareV2.10.215-L0-fullflash.zip).

## An instruction for MacOS users

[AnakChan](https://www.head-fi.org/members/anakchan.194497/) has [published](https://www.head-fi.org/threads/791531/page-1266#post-14613722) the following instruction, based on his successful experience, on how to update to Android Oreo:

**Pre-requisites**

a. Download & install [Etcher](https://en.wikipedia.org/wiki/Etcher_(software))<br />
b. Download & unzip [DX200FirmwareUpdater.zip](https://github.com/Lurker00/DX200-Firmware-Add-on/releases/download/v1.12/DX200FirmwareUpdater.zip)<br />
c. Download & unzip [iBasso’s Oreo](http://ibasso.com/down.php)<br />

**Install Steps**
1. Run the balenaEtcher app
1. Select Image `DX200FirmwareUpdater.img`
1. Select Drive (Pick your microSD card) & Continue
1. Select Flash!
1. Enter your MacOS privileged password
1. Exit balenaEtcher app
1. Physically eject microSD and reinsert
1. MicroSD should mount as `DX200UPDATE`
1. Doubleclick into `DX200UPDATE`
1. Open another Finder window
1. Navigate to the unzipped iBasso Oreo (c) above
1. Go to `DX200-Android8.1-Beta-V2/DX200-Android8.1-Beta-V2`
1. Copy `update.img` to the `DX200UPDATE` finder window
1. Right-click the `sdupdate.img` (Zero bytes) and Move to Bin
1. Right-click `update.img` and Rename to `sdupdate.img`
1. Eject the `DX200UPDATE` MicroSD from Finder
1. Switch off the DX200
1. Put the `DX200UPDATE` MicroSD into the DX200
1. Power on the DX200
1. The DX200 should be “Installing system update”
1. It takes just over 3 mins. The first 50% fo the bar is fast, but the remaining 50% of the bar is slower. It’s not hanging
1. When it finishes, it’ll say :-<br />
    `Supported API: 3`<br />
    `Doing Actions succeeded.please remove the sdcard……`<br />
1. Remove the MicroSD and it’ll auto boot
1. You now have iBasso's Oreo

**For Lurker0's USB Audio/HiByMusic Plug-in**
1. Download and unzip Lurker's [DX200-A8.1-L1.12-sdupdate.zip](https://github.com/Lurker00/DX200-Firmware-Add-on/releases/tag/v1.12)
1. Go in there and copy his `sdupdate.img` (140,052,952 bytes) into the `DX200UPDATE`
1. It's ok to overwrite the iBasso's Oreo `sdupdate.img` (or rename the iBasso's Oreo to whatever, up to you)
1. Eject and follow the same procedures above steps 17-20
1. This time however, the update is very quick < 1 min
1. Eject the MicroSD and let your DX200 reboot
1. Upon coming up Android would say it's updating
1. When finish you should have Lurker0's USB Audio, Magisk Manager, & HibyMusic (Lurker)

