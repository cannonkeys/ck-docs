# Instant60

## Default Layouts and Firmware

The layouts shown are as they look in VIA. Due to a VIA limitation, all keys are shown, even if they are not present on your specific variant of Instant60 (ANSI vs Tsangan). These layouts show which keys don't exist on each variant.

### ANSI
[Default Firmware](assets/cannonkeys_instant60_via_standard.bin)
* Layer 0
![](images/layouts/instant60_ansi_0.jpg)
* Layer 1
![](images/layouts/instant60_ansi_1.jpg)


### Tsangan
[Default Firmware](assets/cannonkeys_instant60_via.bin)
* Layer 0
![](images/layouts/instant60_ansi_0.jpg)
* Layer 1
![](images/layouts/instant60_ansi_1.jpg)

## Using VIA

!!! Notice
    VIA support is built in to the default firmware, but the VIA software will not support the board until Late June (ETA). If you need to change the layout in the meantime, you will have to compile and flash the firmware.

To change the keymap, simply open VIA Configurator and it will load the keyboard. If it does not work, restart VIA. From there, it's intuitive to change keys.

## Building Firmware

### Easy Option

!!! Notice
    There is a known bug with QMK Configurator which should be fixed in the upcoming weeks which causes it to build improper bin files. 

The easy option to create firmware is to use [QMK Configurator](https://config.qmk.fm/#/cannonkeys/instant60/LAYOUT_ansi).
This will give you a graphical interface for creating your desired keymap.

### More Hands-on Option

If you'd like to customize more than just a keymap, the best place to start is the [QMK Newbs Guide](https://docs.qmk.fm/#/newbs).
Follow the guide up until the flashing portion, and then follow the flashing guide below.

## Flashing
### One Time Setup 

Once the steps in this section are done once, they will not have to be done again, unless your driver resets.

1. Install the newest release of Zadig from [https://zadig.akeo.ie/](https://zadig.akeo.ie/).
1. Download the newest release of QMK Toolbox from [https://github.com/qmk/qmk_toolbox/releases](https://github.com/qmk/qmk_toolbox/releases)
1. Change the switch to "1" on the PCB
    ![](images/initial_flash/switch1.jpg)
1. Plug the PCB in
    ![](images/initial_flash/plug-in.jpg)

1. Open Zadig
    ![](images/initial_flash/ZadigNormal.PNG)
1. Click "List all Devices" in the Options menu
    ![](images/initial_flash/ZadigListAll.PNG)
1. Select "STM32 BOOTLOADER" from the device dropdown
    ![](images/initial_flash/ZadigSTM32.PNG)
1. Select WinUSB from the Driver dropdown
    ![](images/initial_flash/ZadigWinUSB.PNG)
1. Click the 'Replace Driver' Button
    ![](images/initial_flash/ZadigReplace.PNG)
1. You should see a "Installing Driver" progress bar appear
    ![](images/initial_flash/ZadigInstallingDriver.PNG)

### Flashing

After initial setup has been done once, you can use the RESET keycode in QMK to enter flashing mode on your PCB. From there:

1. Download the proper firmware for your PCB
1. Start QMK Toolbox, and click the "Open" buttom
    ![](images/initial_flash/QMKToolbox.PNG)
1. Change the filetype dropdown to ".bin" and select the proper firmware
    ![](images/initial_flash/QMKToolboxBIN.PNG)
1. Hit the "Flash" Button
    ![](images/initial_flash/QMKToolboxFlash.PNG)
1. At the end, you should see "File downloaded successfully"
1. Change the switch back to "0" and hit the reset button
    ![](images/initial_flash/switch0.jpg)
1. Verify all the LEDs work
    ![](images/initial_flash/verify.jpg)