# ArchLinux-From-Scratch
A project where I discuss the set up of Arch Linux from scratch. No sudo, no networkmanager, no bash. Nothing.

Done by Jason Okafor.

Device/Machine: Macbook M3 Air (2024, virtualised via UTM)

Aim: to install Arch Linux with no packages, just ~2.6GB of essential CLI software storage

Outcome: Transfer from raw Arch CLI ISO to XFCE GUI desktop (with a nice fastfetch CLI in the process :) )

Extras in the process: setting up networking, fstab, partitioning, mounting, and GRUB

**Intro**

This project briefly covers how I installed Arch Linux from scratch on an Apple M3 Mac, with no scripts and just UTM and the man-pages.

– Avoiding GRUB failing altogether  
– partitioning and mounting manually  
– using systemd and my Mac terminal to set up Arch DNS and network  
– `sudo`ing XFCE (most importantly, of course)  
– constant debugging and surprise emergency mode CLI bootups  

### Boot Process & UEFI
– UTM configured for UEFI  
– Manual ISO boot  
– Learned GRUB fallback via shell + UEFI diagnostics  

### Partitioning & Mounting
– Created `/boot` (vfat) and `/` (ext4) partitions  
– Mounted manually using `lsblk`, `blkid`, and `mount`/`mnt`  
– Verified structure and UUIDs  

### GRUB & Bootloader
– Installed GRUB via chroot  
– Resolved missing `vmlinuz-linux` and EFI var issues  
– Ran `grub-install` + `grub-mkconfig` after fixing `/boot/efi`  

### Networking (systemd)
– Diagnosed broken DHCP + missing DNS  
– Configured `systemd-networkd` manually  
– Created `.network` unit files and brought up interface  
– Set DNS manually via `/etc/resolv.conf`  

### GUI Setup
– Installed `xorg`, `xfce4`, and `lightdm`  
– Edited `~/.xinitrc` for startxfce4  
– Rebooted into working GUI session  

### Package Management Recovery
– Fixed pacman mirror sync issues  
– Used `reflector`, `timedatectl`, and `pacman -Syy`  
– Unlocked stale database locks  

