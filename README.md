# EOL
My Laptop is broken. This repo is End-of-life.

# Dell-G3-3579-Hackintosh-OpenCore
My OpenCore EFI folder backup

My OpenCore is configured as a "macOS Launcher", I use rEFInd as Boot Menu.

I'm trying to install macOS Big Sur. Focus [this branch](https://github.com/CerteKim/Dell-G3-3579-3779-Hackintosh-OpenCore/tree/bigsur)

# Instructions

## Install gibMacOS and create boot USB

Follow this [guide](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/winblows-install.html#making-the-installer) to create a USB installer for macOS

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
* ~~Intel Wireless AC9462~~  Replace with DW1820A
* ALC236
* ~~Intel 600P~~ Replace with Samsung SM961
* Thunderbolt

## Working
Boot Installation Media

## Not working
* dGPU (Disabled by SSDT, I will try to make it work on my [another project](https://github.com/CerteKim/Dell-G3-3579-HackintoVM))  
