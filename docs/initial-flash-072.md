# Flashing onboard MCU Boards (Initial)

## One Time Setup 
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

## Flashing
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