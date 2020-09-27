# Mks-Robin-Nano-Marlin2.0-Firmware
## Features
The firmware of Mks Robin Nano, based on [Marlin2.0.x](https://github.com/MarlinFirmware/Marlin)(The based version is based on Marlin2.0 bugfix) and the below by   
alpine https://github.com/inib/Marlin/blob/2.0.X-SapphirePro-3.5TFT/

### see the blog Below

https://escope.de/posts/sapphire-pro-marlin/

#### **Vanilla Marlin Touch UI**

Settings for the Two tree's Sappire S PRO

This is a Alpha test

It is developed on PlatformIO, we hope more and more developers will participate the development of this repository.


## Build
As the firmware is based on Marlin2.0.x which is built on the core of PlatformIO, the buid compiling steps are the same as Marlin2.0.x. You can directly using [PlatformIO Shell Commands](https://docs.platformio.org/en/latest/core/installation.html#piocore-install-shell-commands), or using IDEs contain built-in PlatformIO Core(CLI), for example, [VSCode](https://docs.platformio.org/en/latest/integration/ide/vscode.html#ide-vscode) and [Atom](https://docs.platformio.org/en/latest/integration/ide/atom.html). VSCode is recommended.


## MKS Robin Nano V1.2 build and update firmware

1. Build config:
     
- `default_envs = mks_robin_nano35`     
- `#define MOTHERBOARD BOARD_MKS_ROBIN_NANO`    
- `#define TFT_LVGL_UI_FSMC`

2. Update firmware:
   
- Enter the `.pio\build\mks_robin_nano35` directory, copy the `assets` folder and `Robin_nano35.bin` to the sd card
- SD card is connected to the motherboard, and you can see the update interface after powering on.   

## MKS Robin Nano V2.0 build and update firmware

1. Build config:
     
- `default_envs = mks_robin_nano35`     
- `#define MOTHERBOARD BOARD_MKS_ROBIN_NANO_V2`    
- `#define TFT_LVGL_UI_SPI`

2. Update firmware:
   
- Enter the `.pio\build\mks_robin_nano35` directory, copy the `assets` folder and `Robin_nano35.bin` to the sd card
- SD card is connected to the motherboard, and you can see the update interface after powering on.   

## Others functional configuration
Please refer to [MKS-Robin-Nano-V2 wiki](https://github.com/makerbase-mks/MKS-Robin-Nano-V2/wiki/Marlin_firmware).

## More information about the Robin Nano
Please refer to [MKS Robin Nano github](https://github.com/makerbase-mks/MKS-Robin-Nano).