# Dell-G3-3579-Hackintosh-OpenCore
My OpenCore EFI folder backup

My OpenCore is configured as a "macOS Launcher", I use rEFInd as Boot Menu.

Using OpenCore version X.X.X

# Instructions

## Create MacOS USB boot device

Follow this [guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) to create a USB installer for macOS

## Copy files over

Replace the EFI/OC folder with the one supplied in this repository

## Boot the USB 

Using the BIOS, load the USB

## Setup_var by using my grubx64.efi

Set these variables inside the grub shell
```
setup_var 0x5BC 0x0 //Disable CFG Lock
setup_var 0x8C9 0x2 //Set DVMT Pre-Allocated to 64M
```

Exit out of the grub shell

## Load macOS installer

Load the macOS installer and go through the steps to install into a new hard drive partition

# Hardware Configuration
* i7 8750H
* UHD630
* GTX1060 max-q
* Intel Wireless AC9462
* ALC236
* Thunderbolt

## Working
Boot Installation Media

## Edit config.plist

Use https://anyplist.com/#/  

## Not working
* dGPU (Disabled by SSDT, I will try to make it work on my [another project](https://github.com/CerteKim/Dell-G3-3579-HackintoVM))  
