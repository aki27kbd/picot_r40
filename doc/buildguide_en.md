# Build Guide

![picot_r40_main00](/images/main_00.jpg)

This is a build guide for picot_R44.  

picot_R44 is a 40% raw-staggered keyboard using picot5400, which is the original module with RP2040 microcontroller and PMW3600 trackball sensor. 25mm or 34mm trackball is compatible.
To begin with, please make sure you read this build guide carefully and you have everything you need before you start to assemble.


## Parts
### Parts Included

|Parts|No.|Notes|
|---|---|---|
|PCB|1||
|Switch Plate|1||
|picot5400|1||
|Unified Daughter Board|1||
|Sensor (PMW3360)|1||
|JST Cable|1||
|FFC|1||
|[THQWGD001](https://github.com/Taro-Hayashi/THQWGD001)*|3||
|Switch Socket|40||
|M2 Spacer 3.5mm|16||
|M2 Screw 3mm|24||
|M2 Screw 5mm|14||
|M2 Nut|6||
|Rubber Feet|4||
|Bearing Roller|3||
|Stainless Pin|3||
|Silicone Tube (Thin)|1||
|Silicone Tube (Thick)|1||
|Magnet|8||
|3D Printed Case|1||
|3D Printed Ball Case (Base + Cover)|1||

*THQWGD001 is designed by Taro Hayashi. Those included in the kit are re-designed for this keyboard.

### Additional Required Parts

|Parts|No.|Notes|
|---|---|---|
|Keyswitch|Max 40|MX|
|Keycap|Max 40|MX|
|2U Stabilizer|2~3||
|Trackball 34mm or 25mm|1||
|USB-TypeC Cable|1||


## Assembly
### Parts Check

  First, please make sure that you have all the parts listed above. If the PCB comes with tabs, break off the tabs and lightly file the cut surfaces.

### picot5400

  Please visit [picot5400 build guide](https://github.com/aki27kbd/picot5400/blob/main/doc/buildguide.md), and solder/assemble parts related to picot5400.  

### PCB

  Solder switch sockets on the PCB.  
  Please select one of two layouts for Enter keys (SW10 or SW10-2).  
  ISO Enter (SW10)
  ![picot_r40_bg_pcb_1](/images/bg_pcb_1.jpg)  

  1.5U BS + 1.25U Enter (SW10-2)  
  ![picot_r40_bg_pcb_2](/images/bg_pcb_2.jpg)  

  Solder encoder pins.    
  Insert encoder from the top of PCB, and solder from the bottom side.  
  ![picot_r40_bg_pcb_3](/images/bg_pcb_3.jpg)  

  Insert a shaft into a wheel.    
  ![picot_r40_bg_pcb_4](/images/bg_pcb_4.jpg)  

  Insert a wheel into the encoder.  
  ![picot_r40_bg_pcb_5](/images/bg_pcb_5.jpg)  

  Put a base part on the other side of the encoder.    
  ![picot_r40_bg_pcb_6](/images/bg_pcb_6.jpg)  

  Fix the base part with a M2 nut and a M2 5mm screw.  
  ![picot_r40_bg_pcb_7](/images/bg_pcb_7.jpg)  

  Put an encoder cover over the encoder.  
  ![picot_r40_bg_pcb_8](/images/bg_pcb_8.jpg)  

  Further steps are the same as picot_O44, please refer to [picot_O44 Build Guide](https://github.com/aki27kbd/picot_o44/blob/main/doc/buildguide.md).

### Firmware

  It is delivered with the default firmware is written. If you wish to write your own firmware, please follow the instructions below.

  - Press the RESET button while holding down the BOOT button on the picot5400 to enter boot loader mode.
  - The firmware is written by dragging and dropping the [.uf2](https://github.com/aki27kbd/picot_r40/blob/main/firmware/aki27_picot_r40_vial.uf2)file into the drive named RPI-RP2.  　

  Keymap is editable from [vial](https://vial.rocks/).  
  You can confirm that keys and trackball are working correctly with this firmware.

  The default firmware enables "Auto Mouse Layer", with which you can automatically jump into a specific mouse layer when you move trackball. You can toggle on/off this function with the custom keycode `AM_TOG`.

  The source code is available [here](https://github.com/aki27kbd/vial-qmk/tree/vial/keyboards/aki27/picot_r40).


## Custom Keycodes

  Several custom key codes can be set for trackball operation.

  Keycode   |Description
  ---------|-----------
  `CPI_SW`  |Change the CPI of the trackball. With the default firmware, each press changes the CPI in the following order: 200 -> 400 -> 800 -> 1600 -> 3200 -> 200....
  `SCRL_SW` |Changes the sensitivity of the sensor in scroll mode. The higher the value, the smaller the amount of scrolling.
  `ROT_R15` |Turns the Y axis of the mouse sensor 15 degrees clockwise.
  `ROT_L15` |Rotate the Y axis of the mouse sensor 15 degrees counterclockwise.
  `SCRL_MO` |	Enables scroll mode for as long as it is pressed.
  `SCRL_TO` |Toggles between scroll mode and mouse mode each time it is pressed.
  `SCRL_IN` |Inverts the scroll direction.
  `AM_TOG` |Toggle the function of auto mouse layer.

  Custom key codes can be set in vial using the custom key code under the User tab.  
  ![CustomKeycode_rev](/images/bg_customkeycode.jpg)



## Notes
If you have any problems, please contact us at[Twitter](https://twitter.com/aki27kbd).

Also, it would be very encouraging if you could upload the completed photos to social networking sites. (If you don't feel comfortable uploading your photos, you can send them directly to us via DM.)

The hashtag is #picot_r40.
