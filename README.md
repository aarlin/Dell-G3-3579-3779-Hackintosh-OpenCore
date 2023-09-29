# OpenCore Hackintosh for Dell G3 3579

[![macOS](https://img.shields.io/badge/macOS-11.7.8-orange)](https://www.apple.com.cn/macos/big-sur-preview/)
[![OpenCore](https://img.shields.io/badge/OpenCore-0.6.9-9cf)](https://github.com/acidanthera/OpenCorePkg)

<img align="right" src="https://is1-ssl.mzstatic.com/image/thumb/Purple116/v4/48/4b/eb/484beb20-2c97-1f72-cc11-081b82b1f920/ProductPageIcon.png/230x0w.webp" alt="Critter" width="230">

## Instructions

### Create MacOS USB boot device

Follow this [guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) to create a USB installer for macOS

1. Create a FAT-32 USB partition  
2. Clone the repository for OpenCorePkg  
   ```bash
   git clone git@github.com:acidanthera/OpenCorePkg.git
   ```
   ```bash
   cd OpenCorePkg/Utilities/macrecovery
   ```
3. Download the recovery image for Big Sur  
   `python macrecovery.py -b Mac-42FD25EABCABB274 -m 00000000000000000 download`  
5. Replace the `EFI` folder with the one supplied in this repository  

![image](https://github.com/aarlin/Dell-G3-3579-3779-Hackintosh-OpenCore/assets/5667435/980bfb75-9150-49ea-8db3-4aa8d2fcc57b)

### Boot the USB 

1. Go into BIOS using F2, and change the Boot Sequence to use the macOS installer USB
2. Choose `MACOS (external) (dmg)` to start installation

### Load macOS installer

1. Partition a new hard drive using Disk Utility for APFS
2. Install Big Sur

### Post Installation Steps

1. Download MountEFI: https://github.com/corpnewt/MountEFI
   ```bash
   git clone https://github.com/corpnewt/MountEFI
   ```
   ```bash
   cd MountEFI
   ```
   ```bash
   chmod +x MountEFI.command
   ```
3. Run `python MountEFI.py`  
4. Choose Option B - `(B. Mount the Boot Drive's EFI)`    
6. Drag and drop EFI from booted USB over to mounted EFI folder  
7. Replace mounted `EFI/Boot` folder with this:  
   `https://github.com/chriswayg/hackintosh-opencore/blob/master/rEFInd-BOOT-folder.zip`
10. Find EFI for Microsoft, drag and drop into mounted EFI  
11. Replace mounted `EFI/OC` with `Post-install OC`, rename to OC
12. Restart and load into BIOS using F2
13. Add Boot Sequence option for rEFInd - `\EFI\BOOT\BOOTx64.efi`.  
    **Note**: This should have `refind.conf` in the same directory

![image](https://github.com/aarlin/Dell-G3-3579-3779-Hackintosh-OpenCore/assets/5667435/626fd0a7-e8a0-4eec-b93e-11ec8e9a2b9d)


## Hardware Configuration

| Specifications | Detail | Working |
| :------------: | :------: | :--------: |
| Model | Dell G3 3579 | ✅ |
| Processor | Intel Core i7-8750H @ 2.20Ghz | ✅ |
| Memory | 16GB TEAMGROUP DDR4 2666Mhz & 4GB SK hynix DDR4 2666Mhz | ✅ |
| NVME SSD | HP SSD EX920 1TB | ✅ |
| SSD | Samsung SSD 860 EVO 500GB | ✅ |
| iGPU | Intel UHD Graphics 630 | ✅ |
| dGPU | NVIDIA GeForce GTX 1060 Max-Q 4G | 🚫 |
| Sound Card | Realtek ALC236 | ✅ |
| Ethernet Card | Realtek RTL8111 | ✅ |
| Wireless Card | Intel Wireless-AC 9462 | ✅ |

* HP SSD EX920 1TB
   * Windows 10 - 500 GB
   * Windows 10 - 500 GB
* Samsung SSD 860 EVO 500GB
   * macOS Big Sur (rEFInd)

## Not working
* dGPU (Disabled by SSDT, I will try to make it work on my [another project](https://github.com/CerteKim/Dell-G3-3579-HackintoVM))
* SD card reader
