# Getting Started

## Requirements:
**-Jetson Orin Nano Developer Kit**
**-Power supply (19 V)**
**-A laptop or PC(Linux, Mac or Windows ) with at least 30 GB of storage space**
**-Target storage (NVMe SSD or UHS-1 sd card 64GB or greater)**
**-A USB flash drive**
## Installation Steps:

Any storage attached to the developer kit can be utilised to install the Jetson Linux onto the kit

If you are using the SD card insert it into the SD card slot.
<img width="100" height="90" alt="IMG_20260827_120343" src="https://github.com/user-attachments/assets/23afd0dd-85be-45db-a5cc-a7f59e52a486" />
If you are using the NVMe SSD unscrew the screw and insert it into the slot on the underside of the board.
<img width="100" height="90" alt="IMG_20260827_120655" src="https://github.com/user-attachments/assets/9e84ca61-b4df-44ec-8d8e-b4558a0452f0" />

### Check the UEFI firmaware version :

1. Connect the Developer kit to an external display through the DisplayPort.
2. Connect the power supply to the board.
3. Repeatedly press **Esc** after the NVIDIA boot splash appears
4. If the firmware is newer than 36.0 continue. 
5. If the firmware is older than 36.0 complete the JetPack 6.x Update Path before booting the jetpack 7.2.1 Jetson ISO

### The following steps are to be completed on the PC/laptop.
--> First download the Jetson BSP installation media ("**Jetson ISO**") image file from [NVIDIA's website](https://developer.nvidia.com/downloads/embedded/l4t/r39_release_v2.1/iso/jetsoninstaller-r39.2.1-2026-08-07-18-30-47-arm64.iso)

--> I have used Balena Etcher to burn the ISO image into the bootable USB stick you can use any other alternatives of your choice
--> ⚠️ Make sure to select the right drive to burn the ISO image to.

### Final Steps

1. Insert the USB stick to the developer kit and boot the Jetson ISO and install Jetson Linux
2. Press "**Y**" and "**Enter**" on the firmware update confirmation .
3. After completion of the capsule update the install continues to the Jetson Linux (BSP) installation 
4. At the Jetson BSP installation GRUB menu, select Install Jetson ISO r39.2.1.
5. Select the target storage device, either the installed microSD card or NVMe SSD.
6. Confirm the install operation.
7. Wait for the installation to complete.
8. Reboot when prompted.

# BSP Setup

Use NVIDIA SDK Manager when you want a guided host-PC workflow for flashing Jetson Linux, updating firmware, and installing JetPack components.

Choose SDK Manager when:
- You have an Ubuntu 20.04 or 22.04 x86_64 host PC available.
- You want to flash firmware and a supported JetPack release in one guided workflow.
- You want to install Jetson Linux directly to a NVMe SSD instead of using a microSD card.
- You need to recover or reflash a developer kit from Force Recovery Mode.
- You prefer a host-driven flow instead of Jetson ISO.

Install SDK Manager on the Ubuntu host PC. For more information, see the [NVIDIA SDK Manager documentation](https://docs.nvidia.com/sdk-manager/)  and the [Download and Run SDK Manager page](https://docs.nvidia.com/sdk-manager/download-run-sdkm/index.html).

If you are using ubuntu 22.04:
```wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-keyring_1.1-1_all.deb```
```sudo dpkg -i cuda-keyring_1.1-1_all.deb```
```sudo apt-get update```
```sudo apt-get -y install sdkmanager```
###launch SDK Manager

```sdkmanager```

## Connecting the target hardware

1. Connect the Developer Kit to your PC (host) with a type C USB cable 
2. Short pin 9(GND) and 10(FC REC) using a jumper pin(safe) or a paperclip(metallic) if the screen remains blank and the board is powered then the short is successful<img width="2360" height="1118" alt="sdkm-carrier-board-topview" src="https://github.com/user-attachments/assets/aff16d40-fbd7-44b6-8284-956e116cb38e" />
<img width="300" height="400" alt="IMG_20260827_125038" src="https://github.com/user-attachments/assets/4630d408-18c5-41a0-9deb-6aedc4c36e8c" />

3. In SDK Manager, select Jetson Orin Nano [8GB developer kit version] and click OK.
4. Clear Host Machine so only the Jetson target remains selected.
5. Click Continue.

## Install Software Components

1. Select the list of components you want to install and proceed.
2. Enter your host PC sudo password when prompted.
3. Download the packages you want on your host as well
4. When the images are ready, SDK Manager opens the flashing prompt.

## Flash
1. In the flashing prompt, select Runtime for OEM Configuration.
2. Select NVMe to flash Jetson Linux to a NVMe SSD, or select SD Card to flash to a microSD card.
3. Click Flash.
4. Remove the jumper pin if still installed 
