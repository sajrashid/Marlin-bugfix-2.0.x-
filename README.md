# Mks-Robin-Nano-Marlin2.0-Firmware
## Features
The firmware of Mks Robin Nano, based on [Marlin2.0.x](https://github.com/MarlinFirmware/Marlin)(The based version is based on Marlin2.0 bugfix) and the below by   
alpine https://github.com/inib/Marlin/blob/2.0.X-SapphirePro-3.5TFT/

### see the blog Below

https://escope.de/posts/sapphire-pro-marlin/

#### **Vanilla Marlin Touch UI**

Settings for the Two tree's Sappire S PRO


#### added bltouch support 

see https://github.com/AIIoT/2.0.x-SapphirePro-BLTouch

##### Somewhat tested on Sappire Pro

see below guide t0 calibrate bltouch/3dtouch

https://locxess.de/3d/BLTouch_Anleitung_englisch.pdf

###### Excerpt

Calibration
These instructions are written to explain how to calibrate using a computer connected through the
USB port to your printer. This process also assumes that the EEPROM has been enabled in Marlin.
From the command window of Repetier Host or Simplify3D etc enter the following:
M851 ; note the number
M851 Z0 ; set the offset to zero
G28
G1 Z0
The LCD display should show Z = 0
From the display go to the Menu then Prepare/Move axis/0.1mm/Move Z
Now move the Z axis slowly down until the nozzle is the right distance from the build plate (folded
piece of paper or thin card).*
Note the Z axis value on the display it should be something like -1.5
M851 Z-1.5 ; to set the offset you got in the previous step.
M500 ; Stores the values in EEPROM so that it is not reset when you power the printer off and on.
Thats it  – you are ready to print.
If you find that you need to increase or decrease the gap then do:
M851 Z-1.4 ; this would make the gap bigger or
M851 Z-1.6 ; this would make the gap smaller
M500 ; to save the value to EEPROM
(remember the -1.4, -1.5 and -1.6 are just examples , yours will be different)
Here is a video of one that is running:
https://www.youtube.com/watch?v=B4yzOQo7iYY
and here https://www.youtube.com/watch?v=9JwNg1mT6u0
* If your firmware isn’t setup to allow negative z movement (#define min_software_endstops false) you will
need to measure/estimate the negative value to enter with the M851 command.


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