# Hackintosh EFI for Dell Inspiron 3543

## Overview
This repository contains the EFI folder and configuration files needed to run macOS Monterey on a Dell Inspiron 3543 laptop. Since there were no comprehensive guides available for this model, this project aims to help others by providing a fully working EFI folder.

### Model Specifications:
| Component       | Specification                             |
| -------------- | ----------------------------------------- |
| Model           | Dell Inspiron 3543                        |
| CPU             | Intel Core i5-5000U @ 2.20 GHz             |
| iGPU            | Intel Graphics (fully working)             |
| dGPU            | NVIDIA 820 (disabled, unsupported)         |
| RAM             | 4GB DDR3 @ 1600 MHz                        |
| Storage         | 250 GB SSD                                |
| Display         | 15.5" (1366 x 768) 60Hz                   |
| Audio           | Realtek ALC255 (via AppleALC)              |
| WiFi & Bluetooth| Intel 5100 (replaced Broadcom, working)    |
| Trackpad        | Working                                   |
| Battery         | Working (SMCBatteryManager)                |

### What Works & What Doesn't
- ✅ Everything except WiFi (initially)
- ❌ No NVIDIA GPU acceleration (as expected)

### WiFi Workaround
The original Broadcom 802.11n WiFi card was not supported on macOS v10 and above. I replaced it with an Intel 5100 card from an old laptop. The WiFi now works perfectly using the **AirportItlwm** kext.

## Instructions for Newbies
If you are new to Hackintosh, follow the [Dortania OpenCore Guide](https://dortania.github.io/OpenCore-Install-Guide/) for a complete understanding of the process. This EFI folder is based on the Dortania guide, so make sure to familiarize yourself with it before proceeding.

### Important Note
For privacy reasons, I have removed the **MLB**, **SystemSerialNumber**, and **SystemUUID** from the `config.plist`. You will need to generate your own using the [**GenSMBIOS**](https://github.com/corpnewt/GenSMBIOS) tool. Follow the Dortania guide on how to properly set these values.

## Installation Instructions
1. Backup your data and create a bootable macOS installer.
2. Replace your WiFi card with the Intel 5100 if necessary.
3. Download this repository and copy the EFI folder to your USB installer.
4. Use the provided EFI folder during the installation process.
5. Follow the standard OpenCore installation process for macOS Monterey.

## Troubleshooting
- If WiFi doesn’t work, check the AirportItlwm kext version.
- Disable the NVIDIA GPU in BIOS if you encounter issues.

## Credits
Special thanks to the Hackintosh community especially [r/Lilobast](https://www.reddit.com/user/Lilobast/) and the Dortania guide for resources and guidance.

