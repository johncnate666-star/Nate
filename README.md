# Iphone stuff
# 
## TABLE OF CONTENTS

1) Palera1n mod by kitty915
2) aurora
3) legacy ios kit
4) idevicerestore 


# Palera1n mod by kitty915

> **Warning** PLEASE, DO NOT ASK FOR SUPPORT REGARDING ICLOUD BYPASS IN PALERA1N DISCORD SERVER! THIS IS NOT OFFICIALLY SUPPORTED AND WON'T EVER BE.

This palera1n mod adds a tethered iCloud Hello screen bypass for checkm8 devices, tested on an iPhone 6S.

The script works on macOS and Linux. Windows is NOT supported. VMs are NOT supported unless PCI USB Passthrough is used. LiveCD Linux can be used if you have enough RAM.

Only tested on tethered palera1n jailbreak, semi-tethered may need different mount directories but I don't have a compatible device to test.

This bypass will also jailbreak with palera1n, we do this to disable rootfs seal enforcement. This could be done without palera1n patching the kernel but I am too lazy to do that, and I want a JB anyways.

iOS 16 support should be working now.

# Known issue

SSH may not work in the bypass phase. This is currently being looked into.

# DISCLAIMER

This bypass must not be used on a device you don't legally own and have permission to modify, I am not responsible for any misuse of anyting in this repo.

# Usage
To bypass Hello screen we will first of all, restore to a clean iOS 15 or 16 version.

You should be in the Hello screen for the version you restored, now reboot into DFU mode.

Now in your PC, clone this git repo (recursively) and cd into it
```
git clone https://github.com/kitty915/palera1n-mod/ && cd ./palera1n-mod/
```

Make sure you have all palera1n dependencies installed, then we can start with the jailbreak and bypass process.

> If you are in linux you may need to run the following commands in a new terminal (and leave it open) before running palera1n:
>
> ``sudo systemctl stop usbmuxd && sudo usbmuxd -p -f``

We will jailbreak with palera1n first to prepare all files:
```
./palera1n.sh --tweaks <iOS version> --verbose
```
>You will need to replace "\<iOS version\>" with the iOS version currently installed in your device. For example:
>
>``./palera1n.sh --tweaks 15.7.1 --verbose``

Let the script run and follow any screen prompt if any. When it finishes you should be booted into iOS again. If for some reason you end up in recovery mode, try running the command again and it should boot you into iOS.

If everything was succesful and you booted into iOS, reboot to DFU again, we are going to start the bypass process.

Type the following command in the terminal:
```
./palera1n.sh --bypass <iOS version>
```
> Again, changing "\<iOS version\>" with your iOS version.

Let the process finish and your device should be in recovery mode

Once in recovery mode, we are already done with the bypass, just run the same palera1n command from before to boot.

```
./palera1n.sh --tweaks <iOS version> --verbose
```
> **Warning** You will have to run this command every time you want to boot your device!
>
> Remember to change "\<iOS version\>" with your iOS version too.

Now, proceed with setup as normal, you can skip Wi-Fi setup and won't be asked to activate your device.

You can now jailbreak with palera1n too with the Tips app, enjoy!

> In case that the JB breaks and you need to restore it, do the following:
> 
> ``./palera1n.sh --restorerootfs <iOS version>``
>
> ``./palera1n.sh clean``
>
> ``./palera1n.sh --tweaks <iOS version> --verbose``
>
> ``./palera1n.sh --bypass <iOS version>``
>
> ``./palera1n.sh --tweaks <iOS version> --verbose``
>
> And you should be booted back in with a clean JB




-----
-----


# Aurora 
![image](https://github.com/Toni-d-e-v/Aurora-Icloud-bypass/assets/62844491/a1f00c97-af2f-4a97-83db-97e6db7a408e)

# Disclaimer

**Important Notice:** This repository and its contents are intended solely for educational purposes. Please exercise caution and discretion when using any information or software provided here. The developers of this software cannot be held liable for any damages incurred through its use. Utilizing any tools from this repository to engage in unauthorized attacks or unlock targets without prior, mutual consent is strictly illegal. It is the responsibility of the end user to comply with all relevant local, state, and federal laws. We assume no liability and bear no responsibility for any misuse or harm resulting from the use of this software.
## How to Run

You can run this script on Mac, Linux, or Windows with the Linux subsystem. Ensure that your device is connected via USB, and then execute the following commands:

```bash
git clone https://github.com/Toni-d-e-v/Aurora-Icloud-bypass-shell && cd Aurora-Icloud-bypass-shell && chmod +x start.sh && clear && ./start.sh;
```

## Features

This repository offers several functionalities for various purposes:

1. **iCloud Unlocker (ibypass.sh):** This tool assists in iCloud unlocking.

2. **Root Shell for Jailbroken Devices (root_shell.sh):** Provides access to a root shell on jailbroken devices.

3. **Remove Old iCloud Account:** It allows for the removal of old iCloud accounts. Note that after removal, you may need to attempt account addition multiple times and apply various glitching techniques, especially if a passcode is in place.

4. **SIM Fix Scripts (simfrom.sh/simto.sh):** These scripts enable the dumping and restoration of SIM card files. It's important to dump the SIM card files before restoring the device, perform the bypass, and then restore the files. All relevant options are available in the menu.

5. **Remove iCloud Account from Activated Device (rm_oldicloud.sh):** This script can be used to remove an iCloud account from a device that is already activated. Caution: Do not restore the device after using this script.

## About

This script simplifies the process by downloading all necessary components. Follow the provided instructions, and it should work seamlessly on devices supported by the Checkra1n jailbreak, spanning from iPhone 5s to iPhone X. It is compatible with iOS 14, although some iOS 13 versions may not be supported. Enjoy exploring its functionalities!

-----
-----

# legacy ios kit

# Legacy iOS Kit

- (formerly iOS-OTA-Downgrader)
- **An all-in-one tool to [restore/downgrade](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/Restore-Downgrade), [save SHSH blobs](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/Saving-SHSH-blobs), [jailbreak](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/Jailbreaking) legacy iOS devices, and more**
- Supported on **Linux and macOS**
- **Read the ["How to Use" wiki page](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/How-to-Use) for instructions**
- **Read the ["Troubleshooting" wiki page](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/Troubleshooting) for tips, frequent questions, and troubleshooting**

## Features
- Legacy iOS Kit supports all 32-bit iOS devices, and some 64-bit (A7/A8/A9/A10/A11) devices
    - Devices that received iOS 16 and newer will only have limited functionality (e.g. sideloading) and some features like SSH ramdisk are not supported
    - Legacy iOS Kit defines *legacy devices* as all iOS devices that are vulnerable to a bootrom exploit (checkm8 and older)
- Restore to signed OTA versions (iOS 8.4.1 and/or 6.1.3) on A5/A6 devices
- Restore to iOS 10.3.3 (signed OTA version) on supported A7 devices
- Restore supported devices to unsigned versions with SHSH blobs
- Restore to unsigned iOS versions with iOS 7 blobs (powdersn0w)
- Restore supported 32-bit devices to unsigned iOS versions "without" blobs
    - Includes downgrading iPhone 2G, 3G, 3GS, iPhone 4 GSM and CDMA, iPod touch 1, 2, 3, iPad 1
    - "without" is in quotes because powdersn0w uses iOS 5/7 blobs for touch 3 and A4 devices, but it is signed for everyone to use
    - Other devices however are true blobless
- Tethered downgrades/restores to supported iOS versions for A5(X)/A6(X) and some other 32-bit devices
- Jailbreak all 32-bit iOS devices on nearly any iOS version
    - Available on iOS versions 3.0 to 9.3.4 with some small exceptions
- Hacktivation for iPhone 2G, 3G, 3GS, 4 GSM (activate without valid SIM card)
- Boot SSH Ramdisk for supported 32-bit and 64-bit devices
- Save Onboard SHSH blobs for supported 32-bit and 64-bit devices
- Sideload IPA files for supported devices on Linux (and macOS)
- Save SHSH blobs from Cydia servers for 32-bit devices
- Enter pwned iBSS/kDFU mode for supported 32-bit devices
- Save onboard SHSH blobs for jailbroken 64-bit devices (deverser)
    - This also saves onboard Cryptex APTicket and seed for iOS 16+ (x8A4)
- Install [TrollStore](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/TrollStore) using SSH Ramdisk for supported 64-bit devices on iOS 14/15
- Clear NVRAM for 32-bit devices
- Device activation using ideviceactivation (especially useful for iOS 4 and lower)
- The latest baseband will be flashed for certain A5/A6 devices (for iPhone 4S, 5, 5C, iPad 4, mini 1)
    - For more info on baseband, go to [Baseband Update](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/Baseband-Update) wiki page
- Dumping and stitching baseband to IPSW (requires `--disable-bbupdate`)
- Dumping and stitching activation records to IPSW (requires `--activation-records`)
- [App Management](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/App-Management) - Install IPA (AppSync), dump apps as IPA, list installed apps
- [Data Management](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/Data-Management) - Backup and restore, mount device, erase all content and settings
- [Misc Utilities](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/Misc-Utilities) - Pair device, export data and battery info, shutdown/restart device, and more

## Supported devices
- [Identify your device here](https://ipsw.me/device-finder)
- **iPhone 5C and iPad mini 3 devices are NOT supported by OTA downgrades**
    - These devices still support restoring to other iOS versions with SHSH blobs, see below
- See the table below for OTA downgrading support:

<table>
    <thead>
        <tr>
            <th>Target Version</th>
            <th>Supported Devices</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=4>iOS 10.3.3</td>
            <td><b>A7 devices:</b></td>
        </tr>
        <tr><td>iPhone 5S</td></tr>
        <tr><td>iPad Air 1</td></tr>
        <tr><td>iPad mini 2 (except iPad4,6)</td></tr>
        <tr>
            <td rowspan=6>iOS 8.4.1</td>
            <td><b>32-bit devices:</b></td>
        </tr>
        <tr><td>iPhone 4S</td></tr>
        <tr><td>iPhone 5</td></tr>
        <tr><td>iPad 2, iPad 3, iPad 4</td></tr>
        <tr><td>iPad mini 1</td></tr>
        <tr><td>iPod touch 5</td></tr>
        <tr>
            <td rowspan=2>iOS 6.1.3</td>
            <td>iPhone 4S</td>
        </tr>
        <tr><td>iPad 2 (except iPad2,4)</td></tr>
    </tbody>
</table>

- Restoring with SHSH blobs, jailbreaking, and using SSH ramdisks are supported on the following devices:
    - iPhone 2G, 3G, iPod touch 1
    - iPhone 3GS, 4, 4S, 5, 5C
    - iPad 1, 2, 3, 4, mini 1
    - iPod touch 2, 3, 4, 5
- Restoring with SHSH blobs and using SSH Ramdisks are also supported on some 64-bit devices:
    - iPhone 5S, 6, 6S, SE 2016, 7 (including Plus variants)
    - iPad Air 1, 2
    - iPad mini 2, 3, 4
    - iPod touch 6, 7
    - Versions that can be restored to depend on SEP/BB compatibility
    - Although SEP/BB compatibility does not matter anymore for A9(X)/A10(X) devices thanks to [turdus merula](https://sep.lol)
- Restoring with iOS 14.3-15.x and 16.6+ SHSH blobs using futurerestore is also supported on these devices (SSH ramdisks not supported):
    - iPhone 8, X
    - iPad 5
    - iPad Pro 9.7/12.9 1st gen
- Restoring with **powdersn0w** is supported on the following devices and target version range:
    - iPhone 4 GSM - iOS 4.0 to 7.1.1
    - iPhone 4 CDMA - iOS 4.2.6 to 7.1.1
    - iPhone 4S, 5, 5C, iPad 2 Rev A, iPod touch 5 - iOS 5.0 to 9.3.5
    - iPad 1 - iOS 3.2 to 5.1
    - iPod touch 3 - iOS 3.1.1 to 5.1
    - Using powdersn0w requires iOS 7.1.x blobs for your device
        - No blob requirement for iPhone 4, iPad 1, iPod touch 3 (7.1.2 and 5.1.1 are signed)
        - For iPhone 5 and 5C, both 7.0.x and 7.1.x blobs can be used
- Restoring **tethered** to any version is supported on the following devices:
    - iPhone 4 (3,2 and 3,3), 4S, 5, 5C
    - iPad 2, 3, 4, mini 1
    - iPod touch 3, 4, 5
- Restoring to other unsigned versions without blobs is supported on the following devices and target version range:
    - iPhone 2G, 3G, 3GS, iPod touch 1, touch 2 - All versions are supported
    - Lowest downgradable version is 2.0. Going to 1.x does not work
    - For jailbreaking support, see below
- [Restoring the iPod touch 3rd gen to iOS 6.0 untethered](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/touch3-ios6)
- [Restoring the iPod touch 4th gen to iOS 7.1.2 tethered](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/touch4-ios7)
- Jailbreaking for 32-bit devices and versions support:
    - iPhone 2G and touch 1 - 3.1.3 only
    - iPhone 3G and touch 2 - 4.2.1, 4.1, and 3.1.3
    - iPhone 3GS - All versions are supported (all release versions from 3.0 to 6.1.6)
    - Other devices - All versions from 3.1.3 to 9.3.4 are supported, with some exceptions
    - For more details, go to the ["Jailbreaking" wiki page](https://github.com/LukeZGD/Legacy-iOS-Kit/wiki/Jailbreaking)


## Supported OS versions/distros

#### Supported architectures: x86_64, arm64

- **macOS** 10.11 and newer
    - macOS 14.6 and newer recommended for Apple Silicon Macs
- [**Ubuntu**](https://ubuntu.com/) 22.04 and newer, and Ubuntu-based distros like [Linux Mint](https://www.linuxmint.com/)
- [**Fedora**](https://getfedora.org/) 40 and newer, Fedora Atomic (Silverblue, Kinoite, etc.) also supported
- [**Debian**](https://www.debian.org/) 12 Bookworm and newer, Sid, and Debian-based distros
- [**Arch Linux**](https://www.archlinux.org/) and Arch-based distros like [EndeavourOS](https://endeavouros.com/) and [CachyOS](https://cachyos.org)
- Less tested distros: [**openSUSE Tumbleweed**](https://get.opensuse.org/tumbleweed/), [**Gentoo**](https://www.gentoo.org/), [**Void Linux**](https://voidlinux.org/)

## Tools and other stuff used
- curl
- bspatch
- [powdersn0w_pub](https://github.com/dora2-iOS/powdersn0w_pub) - dora2ios; [LukeZGD fork](https://github.com/LukeZGD/powdersn0w_pub)
    - [Most of the exploit ramdisks used are from kok3shidoll's repo](https://github.com/kok3shidoll/untitled)
    - [iPhone 5C 7.0.x exploit ramdisk is from m1zole](https://github.com/m1zole/untitled_pub)
    - [Other iPhone 5/5C ramdisks are from Ralph0045's iloader repo](https://github.com/Ralph0045/iloader)
    - [iPad 1 exploit ramdisk is from Ralph0045](https://github.com/Ralph0045/iBoot-5-Stuff)
- [ipwndfu](https://github.com/LukeZGD/ipwndfu) - axi0mX; LukeZGD fork
- [iPwnder32](https://github.com/LukeZGD/iPwnder32) libusb - dora2ios; LukeZGD fork
- [gaster](https://github.com/LukeZGD/gaster) - 0x7ff; LukeZGD fork
- [primepwn](https://github.com/LukeZGD/primepwn)
- [a6meowing](https://github.com/kok3shidoll/a6meowing) - dora/kok3shidoll
- [reipwnder](https://github.com/kok3shidoll/reipwnder) - dora/kok3shidoll
- [daibutsuCFW](https://github.com/LukeZGD/daibutsuCFW) - dora2ios; LukeZGD fork
- [daibutsu](https://github.com/kok3shidoll/daibutsu) - dora/kok3shidoll, Clarity
- [libimobiledevice](https://github.com/LukeeGD/libimobiledevice) - libimobiledevice
- [libirecovery](https://github.com/LukeeGD/libirecovery) - libimobiledevice
- [libideviceactivation](https://github.com/LukeeGD/libideviceactivation) - libimobiledevice
- [ideviceinstaller](https://github.com/LukeeGD/ideviceinstaller) - libimobiledevice
- [ifuse](https://github.com/LukeeGD/ifuse) - libimobiledevice
- [static-cross-openssh](https://github.com/binary-manu/static-cross-openssh) - scp and ssh binaries (used on Linux only)
- [Motrix](https://github.com/agalwood/Motrix) - aria2c binaries
- [usbmuxd2](https://github.com/LukeZGD/usbmuxd2) - tihmstar; LukeZGD fork (used on Linux only, optional)
- [anisette-server](https://github.com/Dadoum/Provision) from Provision - Dadoum (used for sideloading on Linux)
- [AltServer-Linux](https://github.com/NyaMisty/AltServer-Linux) - NyaMisty (used for sideloading on Linux)
- [Sideloader](https://github.com/Dadoum/Sideloader) - Dadoum (used for sideloading on Linux and macOS)
- [tsschecker](https://github.com/1Conan/tsschecker) - tihmstar; 1Conan fork (v413)
- [darkhttpd](https://github.com/emikulic/darkhttpd)
- [x8A4](https://github.com/Cryptiiiic/x8A4) - Cryptiiiic (for getting Cryptex seed)
- [futurerestore](https://github.com/tihmstar/futurerestore) - tihmstar
    - [LukeZGD fork](https://github.com/LukeZGD/futurerestore) used for restoring 32-bit devices (not used in macos arm64)
    - [LukeeGD fork](https://github.com/LukeeGD/futurerestore) used for restoring A7 devices (mostly not used though)
    - [futurerestore nightly](https://github.com/futurerestore/futurerestore/) used for restoring A8/A9/A10/A11 devices
- [iBoot32Patcher](https://github.com/Merculous/iBoot32Patcher/) - Merculous fork
- [idevicerestore](https://github.com/LukeZGD/idevicerestore) - libimobiledevice; LukeZGD fork
- [kloader from Odysseus](https://www.youtube.com/watch?v=fh0tB6fp0Sc)
- [kloader from axi0mX](https://github.com/axi0mX/ios-kexec-utils/blob/master/kloader) (used on iOS 4/5 only)
- [kloader for iOS 5](https://www.pmbonneau.com/cydia/com.pmbonneau.kloader5_1.2_iphoneos-arm.deb)
- [kloader_hgsp from nyan_satan](https://twitter.com/nyan_satan/status/945203180522045440) (used on h3lix only)
- [jq](https://github.com/jqlang/jq)
- [partialZipBrowser](https://github.com/tihmstar/partialZipBrowser)
- [zenity](https://github.com/GNOME/zenity); [macOS build](https://github.com/ncruces/zenity)
- 32-bit bundles from [OdysseusOTA](https://www.youtube.com/watch?v=Wo7mGdMcjxw), [OdysseusOTA2](https://www.youtube.com/watch?v=fh0tB6fp0Sc), [alitek12](https://www.mediafire.com/folder/b1z64roy512wd/FirmwareBundles), [gjest](https://www.reddit.com/r/jailbreak/comments/6yrzzj/release_firmware_bundles_for_ios_841_ipad21234567/) (modified bundles for daibutsuCFW)
- A7 patches from [MatthewPierson](https://github.com/MatthewPierson/iPhone-5s-OTA-Downgrade-Patches)
- iPad 2 iOS 4.3.x bundles from [selfisht, Ralph0045](https://www.reddit.com/r/LegacyJailbreak/comments/1172ulo/release_ios_4_ipad_2_odysseus_firmware_bundles/)
- [datautils0](https://github.com/comex/datautils0) - comex (used for iPad 2 4.3.x kernel diffs)
- [sshpass](https://sourceforge.net/project/sshpass)
- Bootstrap tar from [SpiritNET](https://invoxiplaygames.uk/projects/spiritnet/)
- [Cydia HTTPatch](https://cydia.invoxiplaygames.uk/package/cydiahttpatch) for 3.1.3 downgrades/jailbreaks
- [EverPwnage](https://github.com/LukeZGD/EverPwnage)
- [Lyncis](https://github.com/staturnzz/lyncis)
- [Pangu](https://www.theapplewiki.com/wiki/Pangu)
- [p0sixspwn](https://www.theapplewiki.com/wiki/p0sixspwn)
- [evasi0n7](https://www.theapplewiki.com/wiki/Evasi0n7)
- [evasi0n](https://www.theapplewiki.com/wiki/Evasi0n)
- [g1lbertJB](https://github.com/g1lbertJB/g1lbertJB)
- [UntetherHomeDepot](https://www.theapplewiki.com/wiki/UntetherHomeDepot)
- [greenpois0n](https://github.com/OpenJailbreak/greenpois0n/tree/0f1eac8e748abb200fc36969e616aaad009f7ebf)
- Some patches from [PwnageTool](https://www.theapplewiki.com/wiki/PwnageTool), [sn0wbreeze](https://www.theapplewiki.com/wiki/sn0wbreeze), [redsn0w](https://www.theapplewiki.com/wiki/redsn0w)
- Many patches for the 3GS are made using patchers by Merculous (including [Bundle-Creation](https://github.com/Merculous/Bundle-Creation))
- SSH Ramdisk tars from Ralph0045's [SSH-Ramdisk-Maker-and-Loader](https://github.com/Ralph0045/SSH-Ramdisk-Maker-and-Loader) and msftguy's [ssh-rd](https://github.com/msftguy/ssh-rd)
- 64-bit SSH Ramdisk stuff is based on Nathan's [SSHRD_Script](https://github.com/verygenericname/SSHRD_Script) (iOS 12+), and exploit3dguy's iram tar from [iarchive.app](https://web.archive.org/web/20240324134204/https://ios7.iarchive.app/downgrade/making-ramdisk.html) (iOS 8)
    - [img4lib](https://github.com/xerub/img4lib) - xerub
    - [img4tool](https://github.com/tihmstar/img4tool) - tihmstar
- Tools used for dumping IPA - forks by rcky844
    - [ipainstaller](https://github.com/rcky844/ipainstaller)
    - [Clutch](https://github.com/rcky844/Clutch)
- For iPhone X restore patches:
    - Method by Mineek and Nathan
    - Mineek's [restored_external patcher](https://gist.github.com/mineek/16c2607c928477dcd273e680e40a1c90) for iPhone X downgrades to 14.3-15.x
    - [KPlooshFinder](https://github.com/plooshi/KPlooshFinder/tree/amfi-only)
    - [kerneldiff](https://gist.github.com/LukeZGD/8c719b613ca28d6883552437bdd500de)


-----
-----



# idevicerestore

*A command-line application to restore firmware files to iOS devices.*

![](https://github.com/libimobiledevice/idevicerestore/actions/workflows/build.yml/badge.svg)

## Table of Contents
- [Features](#features)
- [Building](#building)
  - [Prerequisites](#prerequisites)
    - [Linux (Debian/Ubuntu based)](#linux-debianubuntu-based)
    - [macOS](#macos)
    - [Windows](#windows)
  - [Configuring the source tree](#configuring-the-source-tree)
  - [Building and installation](#building-and-installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [Links](#links)
- [License](#license)
- [Credits](#credits)

## Features

The idevicerestore application is a full reimplementation of all granular steps
which are performed during the restore of a firmware to a device.

In general, upgrades and downgrades are possible, however subject to
availability of SHSH blobs from Apple for signing the firmware files.

Some key features are:

- **Restore:** Update firmware on iOS devices
- **Firmware:** Use official IPSW firmware archive file or a directory as source
- **Update:** Allows updating the device by default or erasing all data
- **Download:** On demand download of latest available firmware for a device
- **Cache:** Downloaded firmware files are cached locally
- **Custom Firmware:** Restore custom firmware files *(requires bootrom exploit)*
- **Baseband:** Allows you to skip NOR/Baseband upgrade
- **SHSH:** Fetch TSS records and save them as ".shsh" files
- **DFU:** Put devices in pwned DFU mode *(limera1n devices only)*
- **AP Ticket:** Use custom AP ticket from a file
- **Cross-Platform:** Tested on Linux, macOS, Windows and Android platforms
- **History:** Developed since 2010

**WARNING:** This tool can easily __destroy your user data__ irreversibly.

Use with caution and make sure to backup your data before trying to restore.

**In any case, usage is at your own risk.**

## Building

### Prerequisites

You need to have a working compiler (gcc/clang) and development environent
available. This project uses autotools for the build process, allowing to
have common build steps across different platforms.
Only the prerequisites differ and they are described in this section.

#### Linux (Debian/Ubuntu based)

* Install all required dependencies and build tools:
  ```shell
  sudo apt-get install \
  	build-essential \
  	pkg-config \
  	checkinstall \
  	git \
  	autoconf \
  	automake \
  	libtool-bin \
  	libreadline-dev \
  	libusb-1.0-0-dev \
  	libplist-dev \
  	libimobiledevice-dev \
  	libimobiledevice-glue-dev \
  	libtatsu-dev \
  	libcurl4-openssl-dev \
  	libssl-dev \
  	libzip-dev \
  	zlib1g-dev
  ```
  NOTE: [libtatsu](https://github.com/libimobiledevice/libtatsu) (and thus `libtatsu-dev`)
  is a new library that was just published recently, you have to
  [build it from source](https://github.com/libimobiledevice/libtatsu?tab=readme-ov-file#building).
  Also, other `*-dev` packages might not be available for your distribution,
  so you will have to build these packages on your own as well.

#### macOS

* Make sure the Xcode command line tools are installed.

  **Option 1**:
  The easiest way to build and install `idevicerestore` for macOS is using
  the following build script which will do the work for you, it will build
  and install all required dependencies:
  ```bash
  mkdir -p limd-build
  cd limd-build
  curl -o ./limd-build-macos.sh -L https://is.gd/limdmacos
  bash ./limd-build-macos.sh
  ```
  Follow the prompts of the script and you should have a working `idevicerestore`
  available.

  **Option 2**:
  Use either [MacPorts](https://www.macports.org/)
  or [Homebrew](https://brew.sh/) to install `automake`, `autoconf`, and `libtool`.

  Using MacPorts:
  ```shell
  sudo port install libtool autoconf automake
  ```

  Using Homebrew:
  ```shell
  brew install libtool autoconf automake
  ```

  `idevicerestore` has a few dependencies from the libimobiledevice project.
  You will have to build and install the following:
  * [libplist](https://github.com/libimobiledevice/libplist)
  * [libimobiledevice-glue](https://github.com/libimobiledevice/libimobiledevice-glue)
  * [libusbmuxd](https://github.com/libimobiledevice/libusbmuxd)
  * [libimobiledevice](https://github.com/libimobiledevice/libimobiledevice)
  * [libirecovery](https://github.com/libimobiledevice/libirecovery)
  * [libtatsu](https://github.com/libimobiledevice/libtatsu)

  Check their `README.md` for building and installation instructions.

#### Windows

* Using [MSYS2](https://www.msys2.org/) is the official way of compiling this project on Windows. Download the MSYS2 installer
  and follow the installation steps.

  It is recommended to use the _MSYS2 MinGW 64-bit_ shell. Run it and make sure the required dependencies are installed:

  ```shell
  pacman -S base-devel \
  	git \
  	mingw-w64-x86_64-gcc \
  	make \
  	libtool \
  	autoconf \
  	automake-wrapper \
  	pkg-config \
  	libcurl-devel \
  	mingw-w64-x86_64-libzip
  ```
  NOTE: You can use a different shell and different compiler according to your needs. Adapt the above command accordingly.

  `idevicerestore` has a few dependencies from the libimobiledevice project.
  You will have to build and install the following:
  * [libplist](https://github.com/libimobiledevice/libplist)
  * [libimobiledevice-glue](https://github.com/libimobiledevice/libimobiledevice-glue)
  * [libusbmuxd](https://github.com/libimobiledevice/libusbmuxd)
  * [libimobiledevice](https://github.com/libimobiledevice/libimobiledevice)
  * [libirecovery](https://github.com/libimobiledevice/libirecovery)
  * [libtatsu](https://github.com/libimobiledevice/libtatsu)

  Check their `README.md` for building and installation instructions.


### Configuring the source tree

You can build the source code from a git checkout, or from a `.tar.bz2` release tarball from [Releases](https://github.com/libimobiledevice/idevicerestore/releases).
Before we can build it, the source tree has to be configured for building. The steps depend on where you got the source from.

* **From git**

  If you haven't done already, clone the actual project repository and change into the directory.
  ```shell
  git clone https://github.com/libimobiledevice/idevicerestore.git
  cd idevicerestore
  ```

  Configure the source tree for building:
  ```shell
  ./autogen.sh
  ```

* **From release tarball (.tar.bz2)**

  When using an official [release tarball](https://github.com/libimobiledevice/idevicerestore/releases) (`idevicerestore-x.y.z.tar.bz2`)
  the procedure is slightly different.

  Extract the tarball:
  ```shell
  tar xjf idevicerestore-x.y.z.tar.bz2
  cd idevicerestore-x.y.z
  ```

  Configure the source tree for building:
  ```shell
  ./configure
  ```

Both `./configure` and `./autogen.sh` (which generates and calls `configure`) accept a few options, for example `--prefix` to allow
building for a different target folder. You can simply pass them like this:

```shell
./autogen.sh --prefix=/usr/local
```
or
```shell
./configure --prefix=/usr/local
```

Once the command is successful, the last few lines of output will look like this:
```
[...]
config.status: creating config.h
config.status: config.h is unchanged
config.status: executing depfiles commands
config.status: executing libtool commands

Configuration for idevicerestore 1.1.0:
-------------------------------------------

  Install prefix: .........: /usr/local

  Now type 'make' to build idevicerestore 1.1.0,
  and then 'make install' for installation.
```

### Building and installation

If you followed all the steps successfully, and `autogen.sh` or `configure` did not print any errors,
you are ready to build the project. This is simply done with

```shell
make
```

If no errors are emitted you are ready for installation. Depending on whether
the current user has permissions to write to the destination directory or not,
you would either run
```shell
make install
```
_OR_
```shell
sudo make install
```

**Important**

On Linux, idevicerestore requires a properly installed [usbmuxd](https://github.com/libimobiledevice/usbmuxd.git)
for the restore procedure. Please make sure that it is either running or
configured to be started automatically as soon as a device is detected
in normal and/or restore mode. If properly installed this will be handled
by udev/systemd.

## Usage

The primary scenario is to restore a new firmware to a device.
First of all attach your device to your machine.

Then simply run:
```shell
idevicerestore --latest
```

This will print a selection of firmware versions that are currently being signed
and can be restored to the attached device. It will then attempt to download and
restore the selected firmware.

By default, an update restore is performed which will preserve user data.

Mind that if the firmware file does not contain a 'Customer Upgrade Install'
variant, an erase restore will be performed.

You can force restoring with erasing all data and basically resetting the device
by using:
```shell
idevicerestore --erase --latest
```

Please consult the usage information or manual page for a full documentation of
available command line options:
```shell
idevicerestore --help
man idevicerestore
```

### Docker

Build the container with `build.sh` in the docker folder, which will build a
docker container with the latest source versions of all the required libraries.

Run the container with `run.sh --latest` in the docker folder,
which will execute `usbmuxd` in the background, and then start `idevicerestore --latest`.
Any arguments passed to `run.sh` will be passed in to `idevicerestore`.

## Links

* Homepage: https://libimobiledevice.org/
* Repository: https://github.com/libimobiledevice/idevicerestore.git
* Repository (Mirror): https://git.libimobiledevice.org/idevicerestore.git
* Issue Tracker: https://github.com/libimobiledevice/idevicerestore/issues
* Mailing List: https://lists.libimobiledevice.org/mailman/listinfo/libimobiledevice-devel
* Twitter: https://twitter.com/libimobiledev


