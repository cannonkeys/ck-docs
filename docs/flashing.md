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