# Mks-Robin-Nano-Marlin2.0-Firmware customised for TwoTrees Sappire Pro

## Features
The firmware of Mks Robin Nano, based on [Marlin2.0.x](https://github.com/MarlinFirmware/Marlin)(The based version is based on Marlin2.0 bugfix) and the below by   
alpine https://github.com/inib/Marlin/blob/2.0.X-SapphirePro-3.5TFT/

### Caution Beta Release
*Updated Firmware Binary file*
This Firmware is specific, for the <b>TwoTrees Sappire Pro.</b>
You should ideally compile the binary, for noobs (we are all noobs at some point) I've included the firmware bin file 
From the Firmware folder Copy to Robin_nano35.bin to a sd card and power on/ reboot your printer, firmware should flash straight away, takes less that a minute to complete
*If the process does not start try renaming Robin_nano35.bin to Robin_nano.bin *

### See the blog Below

https://escope.de/posts/sapphire-pro-marlin/

#### **Vanilla Marlin Touch UI**

Settings for the Two tree's Sappire S PRO + BlTouch/3dTouch


#### Added BlTouch/3dTouch support 

See https://github.com/AIIoT/2.0.x-SapphirePro-BLTouch

#### BlTouch/3dTouch Wiring (Robin Nano 1.x)

![alt text](https://github.com/sajrashid/Marlin-bugfix-2.0.x-/blob/master/Images/BltouchWiring.PNG "BltouchWiring")

##### Calibration

See https://locxess.de/3d/BLTouch_Anleitung_englisch.pdf to calibrate bltouch/3dtouch

##### Calibration with GCode

*#define min_software_endstops false* or use negative value get with with the M851 command.

*Ensure Eprom is intialised from Marlin*       

*  M851 ; note the number
*  M851 Z0 ; set the offset to zero
*  G28 ; home all axis
*  G1 Z0; Z axis go to zero position
*  The LCD display should show Z = 0
*  From the display go to the Menu then Prepare/Move axis/0.1mm/Move Z
*  Move the Z axis slowly down until the nozzle is the right distance from the build plate (paper test).*
*  Note the Z axis value on the display it should be something like -1.5
*  M851 Z-1.5 ; to set the offset you got in the previous step.
*  M500 ; Stores the values in EEPROM so that it is not reset when you power the printer off and on.

*  If you need to increase or decrease the gap then do:
*  M851 Z-1.4 ; Make the gap bigger or
*  M851 Z-1.6 ; Make the gap smaller
*  M500 ; to save the value to EEPROM

##### Slicer settings

In your slicer's machine setting start script

add after G28; home all xis

G29; probe bed
G500; Save to Eprom

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