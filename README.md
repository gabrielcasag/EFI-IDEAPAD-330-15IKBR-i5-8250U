# EFI-IDEAPAD-330-15IKB-OPENCORE

## Intro

:warning: **This is not a guide**, please refer to [Dortania](https://dortania.github.io/getting-started) before doing anything. I am not responsible for any damage. This OpenCore configuration is optimized for my specific hardware, so please use it only as a reference or if you happen to have the same or similar hardware.

:information_source: **The current version is fully macOS compatible based on my laptop hardware.**
OpenCore, drivers, and kexts are always up to date!

:information_source: This efi has a hybrid configuration, which means that some kexts are dynamically loaded depending on the macOS (kernel) version. So you can choose the macOS version and use the same EFI.

:information_source: The EFI's have been tested on Catalina, BigSur, Moneterey, Ventura and Sonoma on my IDEAPAD 330 15IKB.

## :computer: Hardware

| **Category** | **Component**                         |
| ------------ | ------------------------------------- |
| **CPU**      | 1.8GHz Intel Core i5-8250u            |
| **GPU**      | Intel UHD 620                         |
| **RAM**      | 20GB (4GB non-removable) 2133MHz DDR4 |
| **SSD**      | 512GB SATA SSD (Netac branded)        |
| **Display**  | 15,6" 1920x1080p non-touch display (Upgraded) |
| **Wi-Fi/BT** | Intel Dual Band Wireless-AC 3165      |
| **Ethernet** | Realtek RTL8111                      |
| **Audio**    | Realtek ALC230 (layout-id=20)         |
| **Input**    | PS2 Keyboard & ELAN TrackPad          |

## macOS Support Table

The table below lists the versions from the EFI of this repo recommended for each version of macOS, strongly recommend to use the [latest](https://github.com/gabrielcasag/EFI-IDEAPAD-330-15IKBR-i5-8250U/releases/latest) one!

| [EFI Releases](https://github.com/gabrielcasag/EFI-IDEAPAD-330-15IKBR-i5-8250U/releases) | [macOS Releases](https://en.wikipedia.org/wiki/MacOS_version_history#Releases) | Demos |  
|-------------|---------------|------|
| >= 0.9.5    | Sonoma        |  [Sonoma Demo](/assets/macos-sonoma.png)  |
| >= 0.8.3    | Ventura       |  [Ventura Demo](/assets/macos-ventura.png)  |
| >= 0.8.0    | Monterey      |  [Monterey Demo](/assets/macos-monterey.png)  |
| >= 0.7.8    | Big Sur       |  🏞️  |
| >= 0.7.8    | Catalina      |  🏞️  |

## :white_check_mark: Working

- [x] CPU power management.
- [x] Graphics acceleration.
- [x] Battery read-out.
- [x] Keyboard & trackpad with all macOS gestures.
- [x] Wi-Fi.
- [x] Bluetooth.
- [x] USB ports.
- [x] HDMI video & audio output.
- [x] Ethernet.
- [x] Audio (Internal speakers, 3.5mm headphone jack).
- [x] Internal microphone.
- [x] VGA WebCam.
- [ ] AirDrop & Handoff.
- [x] iCloud & App Store.
- [x] iMessage & FaceTime.

## :x: Not working

Only AirDrop and Handoff are not working since the Intel card are not fully compatible with macOS. To make these things works you need to replace with a native card one, like the Fenvi cards.

## :closed_lock_with_key: SMBIOS

You will need to generate your own SMBIOS and configure, since is required to fully work with macOS. As per this [guide](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/kaby-lake.html#platforminfo) you can use the following SMBIOS: MacbookPro14,1.

Since the launch of Ventura, I've started using SMBIOS on the MacbookPro15.4 due to its better compatibility compared to the MacbookPro14.1. Another option you could try is MacbookPro15,2.

It's fully **required** to generate your own serials with [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) and put it in your config.plist.

- Config.plist -> PlatformInfo -> Generic

![SMBIOS on config.plist screenchot](/assets/smbios.png "SMBIOS on config.plist screenchot")

## BIOS setup

- Security / Intel Platform Trust Technology - Disabled
- Security / Intel SGX - Disabled
- Security / Secure Boot - Disabled
- Boot / Boot Mode - UEFI

## Steps

1. [Download](https://github.com/gabrielcasag/EFI-IDEAPAD-330-15IKBR-i5-8250U/releases/latest) the latest release;
2. Generate your SMBIOS infos with GenSMBIOS and put on the config.plist;
3. Put the EFI folder on a USB drive with the macOS recovery image or offline image;
4. Install macOS and enjoy :)

## Credits

[**Apple**](http://apple.com/)

[**Acidanthera**](https://github.com/acidanthera)

[**Dortania**](https://dortania.github.io/getting-started/)

[**Gabriel Luchina**](https://luchina.com.br)
