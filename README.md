# Guide to installing macOS on a Thinkpad X240 (With Clover)

## What works
<p></p>

Currently, with all things gathered from various guides, nearly everything works.

## What doesn't work and other problems

- Sound stops working after closing the laptop (fixed with reboot)
- Very rarely, the laptop crashes/kernel panics
- After sleep, very rarely, the SD Card reader stops working (fixed with reboot)
  

## Preparation before installing
<p></p>

### Things required for the installation
- USB Drive (I'd recommend 32GB drive)
- *SPI Programmer (optional)*
- *DW1560 (optional)*
- External mouse 
- External keyboard 
- Your sanity
- A wired connection / an iPhone with a mobile hotspot / a USB with the git repo already downloaded 
### Handoff
If you wish to have handoff with a DW1560 card, you need to flash a new custom BIOS as Lenovo has a whitelist in the BIOS with allowed Wi-Fi cards. To do this, you have to go [here](https://www.techinferno.com/index.php?/forums/topic/12232-lenovo-thinkpad-x240-unlocked-bios-menu-wlan-wi-fi-whitelist-mod/&).
### BIOS Settings
- You need to have memory protection **ENABLED** or else the install USB will **NOT** boot and neither will the system if the settings get reset.
- Have virtualization **ENABLED** (it, overall, boosts performance)
<p></p>

## Guide to installing
<p></p>

#### Pre-install

1. Go to olarila.com and download a premade ISO file (up to Catalina) or download 

2. Download Balena Etcher from balena.io

3. Unzip and flash 
   
#### Install

1. Boot into the USB with UEFI

2. Boot into the install disk

3. After the install boots, enter Disk Utility and format the partition as APFS(otherwise you will run into problems with updates and will have to convert your drive to APFS risking data loss

4. Exit Disk Utility and continue with the install

5. Reboot!

#### Post-install 

1. Plug in the external mouse, keyboard, and the hotspot/flash drive with the files from the git/ ethernet cable

2. Boot with the USB into Macintosh HD (or however you named your macOS drive)

3. Put the kexts from the kexts folder in /Library/Extensions (See Options)

4. Mount the EFI partition, delete everything, and paste the EFI folder from the git repo

5. Open terminal and type sudo kextcache -i /

## **THE NETWORK KEXTS IS FOR THE DW1560 WIFI CARD**
<p></p>
If you want to use the Intel Wifi Card, you should download the itlwm network kexts and replace the kexts I have installed.
<p></p>

## Congratulations! You just installed macOS.

