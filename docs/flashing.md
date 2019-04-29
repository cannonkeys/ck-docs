# Flashing Guide

## Blue-pill Based:
This includes the Practice60, Ortho60, and Ortho48

!!! Note
    At the moment, QMK Toolbox does not support Blue-pill based boards. Work is being done to make the flashing process easier.
    In the meantime, this is the easiest way to flash.

 1. Before flashing, you must have a `.bin` file with your firmware. For more information on how to get the proper firmware, visit the [firmware guide](firmware.md). You will also need a second keyboard for the time being.
 1. To flash a blue pill based board, you will need [dfu-util](http://dfu-util.sourceforge.net/). Download it following the directions on the dfu-util site.
 1. If you're on Windows you'll also have to download [this zip](assets/win_driver.zip) and run `install_drivers.bat`. Windows actually comes with the proper drivers, they're just not properly associated with the Blue Pill's USB ID, so this will do that.
 1. `dfu-util` is a command line tool, so we will have to open a command line to run it. On Windows, open Command Prompt. On Mac OS X, open Terminal. If you're using linux, you probably already know how to open a terminal!
 1. Navigate to the directory you have `dfu-util` installed using `cd` to change directories and `dir` (Windows) or `ls` (Linux) to list files. 

    !!! Example
        If your dfu-util was installed in Downloads, open command prompt and run `cd Downloads` to get to the correct folder. Verify you're in the right place by using `dir`. Make sure `dfu-util.exe` shows up in the `dir` output!

 1. Put your keyboard into flashing mode. You can do this by hitting the reset button on the keyboard, or by using the RESET key, if it's been mapped. At this point, the keyboard you are flashing will no longer work as a keyboard, so you'll have to use a 2nd keyboard for the next steps.
 1. Figure out the path to your firmware. In Windows Explorer, you can do this by navigating to your firmware, and following the instructions on [this page](https://www.pcworld.com/article/251406/windows_tips_copy_a_file_path_show_or_hide_extensions.html) to copy the file path.
 1. Run `dfu-util.exe -d 1eaf:0003 -a 2 -D "\path\to\firmware.bin"`, replacing `\path\to\firmware.bin` with the path you found on the last step.
 1. Congrats! You should see `File downloaded successfully` and you have flashed new firmware onto your keyboard! Either unplug and re-plug your board, or hit the hardware reset button to exit flashing mode.
 
    !!! Note
        On some systems after the flashing finishes, you'll see `Error sending completion packet`, as well as 97% completion. This can be safely ignored!

## Reflashing the bootloader on a Blue-pill
If you flashed your Blue-pill and blew away your bootloader somehow, you'll find yourself needing to reflash your bootloader.

### Mac OS

#### Requirements
To reflash your bootloader on Mac OS, you first need `st-flash` and possibly `openocd` to unlock your blue pill, in addition to your [ST-Link][stlink]. `st-flash` (via `stlink`) and `openocd` can be installed from Homebrew.

```
brew install openocd stlink
```

#### Flashing the bootloader

The first thing you'll need to do is hook your ST Link into your Blue-pill. For some reason, on Mac OS, you may need to swap the SWDIO and SWCLK pins. Additionally, you may need to update your ST-Link's firmware
with [STSW-LINK007][stlink007]. You'll also need the [bootloader binary][bootloader]

1. Ensure that your Blue-pill is recognized by running `st-info --probe`
    * if the `chipid` is `0x0000`, swap the SWDIO and SWCLK pins
    * if the `chipid` is `0x0410`, you're connected correctly
1. Attempt to flash the bootloader using `st-flash --reset --format binary write path/to/generic_boot20_pc13.bin 0x8000000`
    * if you get a `Unknown memory region` error message, you'll need to unlock the chip with the following command then unplug your ST Link to reboot the Blue-pill:

```
openocd -f interface/stlink-v2.cfg \
    -f target/stm32f1x.cfg \
    -c "init; reset halt; stm32f1x unlock 0; reset halt; exit"
```

 If you see the following (or something similar), your Blue-pill was successfully flashed

```
st-flash 1.5.1
2019-04-28T19:58:23 INFO common.c: Loading device parameters....
2019-04-28T19:58:23 INFO common.c: Device connected is: F1 Medium-density device, id 0x20036410
2019-04-28T19:58:23 INFO common.c: SRAM size: 0x5000 bytes (20 KiB), Flash: 0x10000 bytes (64 KiB) in pages of 1024 bytes
2019-04-28T19:58:23 INFO common.c: Attempting to write 7160 (0x1bf8) bytes to stm32 address: 134217728 (0x8000000)
Flash page at addr: 0x08001800 erased
2019-04-28T19:58:23 INFO common.c: Finished erasing 7 pages of 1024 (0x400) bytes
2019-04-28T19:58:23 INFO common.c: Starting Flash write for VL/F0/F3/F1_XL core id
2019-04-28T19:58:23 INFO flash_loader.c: Successfully loaded flash loader in sram
7/7 pages written
```

Now you should have a reflash bootloader ready to be flashed with the QMK firmware of your choosing!

[stlink]: https://cannonkeys.com/products/st-link
[stlink007]: https://www.st.com/en/development-tools/stsw-link007.html
[bootloader]: https://github.com/rogerclarkmelbourne/STM32duino-bootloader/blob/master/bootloader_only_binaries/generic_boot20_pc13.bin
