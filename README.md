# Dell-G3-3579-Hackintosh-OpenCore
My OpenCore EFI folder backup

My OpenCore is configured as a "macOS Launcher", I use rEFInd as Boot Menu.

Using OpenCore 0.6.9, macOS Big Sur 11.7.8

# Instructions

## Create MacOS USB boot device

Follow this [guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) to create a USB installer for macOS

Replace the EFI/OC folder with the one supplied in this repository

![image](https://github.com/aarlin/Dell-G3-3579-3779-Hackintosh-OpenCore/assets/5667435/980bfb75-9150-49ea-8db3-4aa8d2fcc57b)

## Boot the USB 
Go into BIOS using F2, and change the boot options to use the macOS installer USB

## Load macOS installer

Load the macOS installer and go through the steps to install into a new hard drive partition

## Post Installation Steps

1. Download mountEFI: https://github.com/corpnewt/MountEFI
   ```bash
   git clone https://github.com/corpnewt/MountEFI
   cd MountEFI
   chmod +x MountEFI.command
   ```
3. Run `python MountEFI.py`  
4. Choose Option B (B. Mount the Boot Drive's EFI)  
5. Drag and drop EFI from booted USB over to mounted EFI folder  
6. Replace `EFI/Boot` folder with this: https://github.com/chriswayg/hackintosh-opencore/blob/master/rEFInd-BOOT-folder.zip  
7. Find EFI for Microsoft, drag and drop into EFI as well

![image](https://github.com/aarlin/Dell-G3-3579-3779-Hackintosh-OpenCore/assets/5667435/626fd0a7-e8a0-4eec-b93e-11ec8e9a2b9d)


## Hardware Configuration
* i7 8750H
* UHD630
* GTX1060 max-q
* Intel Wireless AC9462
* ALC236
* Thunderbolt

* 1 TB NVME M.2 SSD
   * Windows 10 - 500 GB
   * Windows 10 - 500 GB
* 500 GB SSD
   * macOS Big Sur (rEFInd)

## Working
Boot Installation Media

## Edit config.plist

Use https://anyplist.com/#/  

## Not working
* dGPU (Disabled by SSDT, I will try to make it work on my [another project](https://github.com/CerteKim/Dell-G3-3579-HackintoVM))  
