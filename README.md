# Debian-13-iso-scan-support
Providing additional functionality for diskless booting & installation of Debian Trixie via GNU GRUB. It is possible booting official Debian Installation (live) media diskless via GNU GRUB, but it is not possible installing the system via Debian Installer. This repository provides config and image files for this installation scenario.
This solution was triggered by this bug report https://github.com/Mexit/MultiOS-USB/issues/77 and adopted to MultiOS-USB as a 'one-click-solution', but is usable with any grub2 loopback setup. All files used for the initrd "iso-scan-13.X.0.gz" are provided by Debian Project (Debian 13 "trixie" see: [here](https://github.com/Rockets31/Debian-13-iso-scan-support/blob/main/docs/README_inst)).

# Features
- Filesystems: exfat, ext4
- Scan for devices & ISO files ('iso-scan')
- Provide full debian boot menu
- Supported ISOs: Debian-DVD-1, Debian-netinst & all Debian-live images of Debian 13.6.0 & 13.7.0 release cycles.

# Usage
Load provided 'iso-scan-13.X.0.gz' along with the main 'initrd.gz' of the installation media via grub loopback module. This adds necessary functionality for installing Debian 13.X via debian installer. If you are using 'https://github.com/Mexit/MultiOS-USB', it is just a few steps:

0. Use MultiOS-USB partition on 'exfat' or 'ext4' filesystem.
1. Copy your Debian-13.X.0-iso files to 'ISOs' directory.
2. Copy 'iso-scan-13.X.0.gz' file to MultiOS-USB partition, so it is next to 'ISOs' & 'MultiOS-USB' directory.
3. Create a directory for 'grub.cfg' files e.g.: '/MultiOS-USB/config_priv/debian-iso-scan'
4. Copy 'debian-13.X.0-amd64_d-i.cfg' and 'debian-13.X.0-amd64-live_d-i.cfg' there.
5. Reboot into 'MultiOS-USB' and start e.g. 'debian-13.X.0-amd64-DVD-1.iso [config_priv]' entry.
6. The installer will scan for devices & iso files and you have to select it.

# Screenshots
<img width="1080" height="450" alt="iso-scan_ask_device_0-cut" src="https://github.com/user-attachments/assets/e6b0c205-84c6-441b-908c-7bdc4adf4295" />

<img width="1080" height="450" alt="iso-scan_ask_which_iso_0-cut" src="https://github.com/user-attachments/assets/e9661a6f-2401-4053-b800-c789cdfc25c9" />

<img width="1080" height="800" alt="grub-dark-lang2" src="https://github.com/user-attachments/assets/136d5955-c799-48ed-9f71-c91ebf25681a" />




