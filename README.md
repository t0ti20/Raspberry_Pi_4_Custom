# Raspberry Pi 4 Custom Image

This repository contains a manually built custom image for Raspberry Pi 4, created step-by-step from toolchain setup to the root file system.

## Contents
```BASH
     .
     ├── README.md
     ├── boot
     │ ├── Image
     │ ├── Root
     │ ├── bcm2711-rpi-4-b.dtb
     │ ├── boot.scr
     │ ├── cmdline.txt
     │ ├── config.txt
     │ ├── fixup4.dat
     │ ├── start4.elf
     │ ├── u-boot.bin
     │ └── uRamdisk
     └── rootfs
     ├── bin
     ├── dev
     ├── etc
     ├── home
     ├── lib
     ├── lib64
     ├── linuxrc
     ├── proc
     ├── sbin
     ├── sys
     ├── tmp
     ├── usr
     └── var
```

## What I Did

### 1. Toolchain

I used Crosstool-ng to obtain the toolchain for cross-compilation. This toolchain is essential for compiling various components of the Raspberry Pi image.

### 2. Bootloader

To handle the booting sequence of the Raspberry Pi, I downloaded the necessary firmware files from the vendor, following the booting sequence of the Raspi. I utilized U-Boot as a secondary bootloader to enhance flexibility.

### 3. Kernel

For the kernel, I downloaded the latest version from Linus Torvalds' repository. I configured it with the default settings for Raspberry Pi and compiled it using the toolchain I built in the first step.

### 4. Root Filesystem

To generate the root filesystem, I employed BusyBox, incorporating essential binaries to create a minimal but functional file system.

## How to Use

1. Clone the repository:

   ```bash
   git clone https://github.com/t0ti20/Raspberry_Pi_4_Custom
   ```

2. Follow the steps outlined in the repository's structure to copy the contents of the boot and rootfs directories to the respective partitions of your Raspberry Pi's SD card.

3. Insert the SD card into your Raspberry Pi 4 and power it on.

## Notes
- The boot directory contains bootloader-related files and configurations.
- The rootfs directory includes the root file system generated with BusyBox.
- Feel free to customize and enhance this image according to your project requirements.

Make sure to replace "your-username" with your actual GitHub username. If you have any additional details or notes you'd like to include, please let me know!
