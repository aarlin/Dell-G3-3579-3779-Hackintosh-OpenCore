# OpenCore Hackintosh for Dell G3 3579

[![macOS](https://img.shields.io/badge/macOS-11.7.8-orange)](https://www.apple.com.cn/macos/big-sur-preview/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.6.9-9cf)](https://github.com/acidanthera/OpenCorePkg)

<img align="right" src="https://support.apple.com/content/dam/edam/applecare/images/en_US/macos/psp-mini-hero-macos-high-sierra-whats-new_2x.png" alt="Critter" width="250">

## Instructions

### Create MacOS USB boot device

Follow this [guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) to create a USB installer for macOS

Replace the EFI/OC folder with the one supplied in this repository

![image](https://github.com/aarlin/Dell-G3-3579-3779-Hackintosh-OpenCore/assets/5667435/980bfb75-9150-49ea-8db3-4aa8d2fcc57b)

### Boot the USB 
Go into BIOS using F2, and change the boot options to use the macOS installer USB

### Load macOS installer

Load the macOS installer and go through the steps to install into a new hard drive partition

### Post Installation Steps

1. Download MountEFI: https://github.com/corpnewt/MountEFI
   ```bash
   git clone https://github.com/corpnewt/MountEFI
   cd MountEFI
   chmod +x MountEFI.command
   ```
3. Run `python MountEFI.py`  
4. Choose Option B - `(B. Mount the Boot Drive's EFI)`    
6. Drag and drop EFI from booted USB over to mounted EFI folder  
7. Replace mounted `EFI/Boot` folder with this: https://github.com/chriswayg/hackintosh-opencore/blob/master/rEFInd-BOOT-folder.zip  
8. Find EFI for Microsoft, drag and drop into mounted EFI  
9. Replace mounted `EFI/OC` with `Post-install OC`, rename to OC

![image](https://github.com/aarlin/Dell-G3-3579-3779-Hackintosh-OpenCore/assets/5667435/626fd0a7-e8a0-4eec-b93e-11ec8e9a2b9d)


## Hardware Configuration

| Specifications | Detail | Working |
| :------------: | :------: | :--------: |
| Model | Dell G3 3579 | ✅ |
| Processor | Intel Core i7-8750H @ 2.20Ghz | ✅ |
| Memory | 8GB Micron DDR4 2666Mhz | ✅ |
| SSD | Hikvision C2000Pro 512GB | ✅ |
| HDD | WD10SPZX 1TB | ✅ |
| iGPU | Intel UHD Graphics 630 | ✅ |
| dGPU | NVIDIA GeForce GTX 1060 Max-Q 4G | 🚫 |
| Sound Card | Realtek ALC236 | ✅ |
| Ethernet Card | Realtek RTL8111 | ✅ |
| Wireless Card | Intel Wireless-AC 9462 | ✅ |

* 1 TB NVME M.2 SSD
   * Windows 10 - 500 GB
   * Windows 10 - 500 GB
* 500 GB SSD
   * macOS Big Sur (rEFInd)

## Edit config.plist

Use https://anyplist.com/#/  

## Not working
* dGPU (Disabled by SSDT, I will try to make it work on my [another project](https://github.com/CerteKim/Dell-G3-3579-HackintoVM))  
