# Asus TUF Z390-PRO Gaming Hackintosh - OpenCore - Sonama 14.6.1

[![macOS](https://img.shields.io/badge/macOS-Sonama-brightgreen.svg)](https://developer.apple.com/documentation/macos-release-notes)
[![OpenCore](https://img.shields.io/badge/OpenCore-1.0.0-blue)](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.9.7)

![Screenshot 2024-08-21 at 2 40 37 PM](https://github.com/user-attachments/assets/27136383-fd31-4824-9840-568d12262a31)


## Hardware

| Category   | Component                             |
| ---------- | ------------------------------------- |
| CPU        | Intel Core i9 9900k                   |
| CPU Cooler | Gamemaxx IceBerg 240mm Water Cooling  |	
| Memory     | HyperX 32GB DDR4 3200                 |
| Mobo       | Asus TUF Z390 Pro Gaming LGA1151      |
| GPU        | AMD Radeon Vega 64 8GB / Intel HD 630 |
| SSD        | WD SSD SDBPNTY 512 GB                 |
| WiFi & BT  | Auros WBAX210 WiFi6E                  |
| Ethernet   | Intel I219-V                          |
| Power Supply| SilverStone 750W Strider Platinum	 |
| Case 		 | Gamemaxx Blackhole Mid-Tower			 |
| Monitor    | Samsung Odyssey G50 2K Display        |
| Keyboard   | Logitech MX Mini Keys via Bolt USB    |
| Mouse      | Logitech MX Anywhere 3 via Unified USB|
| Bluetooth	 | Asus BT-400 USB Dongle				 |
<<<<<<< HEAD


## Disclaimer
This guide only applies to the Asus Z390-Pro Gaming motherboard. I am NOT liable for any damage you create to your device. This guide is provided "as-is," and every action you take is at your own risk.

## Installation | Create Install Media | Configure and install OpenCore | GenSMBIOS
I followed the guide from the repo from [alieneotor](https://github.com/alienator88/ASUS-TUF-Z390M-Pro-Gaming-Hackintosh-OpenCore/tree/Ventura) since we have similar hardware.

### Configure OpenCore
In this part, we have to go to the [Opencore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/) repo and review all the details that will work for our hardware. Under Config follow Coffee Lake Config.plist.

## BIOS Settings
Note: Most of these options may not be present in your firmware, we recommend matching up as closely as possible but don't be too concerned if many of these options are not available in your BIOS
### Disable
- Fast Boot
- Secure Boot
- Serial/COM Port
- Parallel Port
- VT-d (can be enabled if you set DisableIoMapper to YES)
- Compatibility Support Module (CSM) (Must be off in most cases, GPU errors/stalls like gIO are common when this option is enabled)
- Thunderbolt (For initial install, as Thunderbolt can cause issues if not setup correctly)
- Intel SGX
- Intel Platform Trust
- CFG Lock (MSR 0xE2 write protection)(This must be off, if you can't find the option then enable AppleXcpmCfgLock under Kernel -> Quirks. Your hack will not boot with CFG-Lock enabled)
### Enable
- VT-x
- Above 4G Decoding
- Hyper-Threading
- Execute Disable Bit
- EHCI/XHCI Hand-off
- OS type: Windows 8.1/10 UEFI Mode (some motherboards may require "Other OS" instead)
- DVMT Pre-Allocated(iGPU Memory): 64MB or higher
- SATA Mode: AHCI

### Troubleshooting tips
Installation boot part: You might need to press space in order to see the installer, as in later versions of OpenCore HideAuxiliary is enabled by default.

In the installation process if it IS going through a loop process you might need to disable some kext and security settings, I saw this from youtube [TechNolLi HACKINTOSH IS OVER](https://youtu.be/Z9va5xRtuvw?t=477)
