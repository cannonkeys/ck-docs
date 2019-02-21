# Build Guide for the Practice60, Ortho60, and Ortho48

These three boards are all Bluepill based. While the guide photos were taken with the Practice60, the steps still apply for the Ortho60 and Ortho48 as well.

Any differences will be called out inside this guide.

!!! Note
    Before starting this build, you should [flash](flashing.md) your Blue Pill using a Micro USB cable, and also [test your Blue Pill](bluepill-test.md)

## Setup
1. Starting Kit:
![](images/build_guide/0-kit.jpg)
1. Tools:
![](images/build_guide/1-tools.jpg)
## Diodes
1. First step - diodes. They are all marked with "D" on the back of the PCB. I suggest soldering them on the back of the PCB.
![](images/build_guide/2-diode-pads.jpg)
1. Bend your diodes around your finger for easy insertion.
![](images/build_guide/3-diode-bent.jpg)
1. The black band on the diode should face the SQUARE pad - on all CannonKeys PCBs it means pointing down. 
![](images/build_guide/4-diode-insert.jpg)
1. Solder the diodes once they've been inserted
![](images/build_guide/5-diode-solder.jpg)
1. Then use your flush cutters to cut the legs. Make sure you save them for a later step!
![](images/build_guide/6-diode-clipped.jpg)
1. Finish soldering all the diodes. At the end, your board should look like this:
![](images/build_guide/7-diode-finished.jpg)

## MOSFET for Backlighting (Optional)

!!! Optional
    These next few steps coming up are optional, and only necessary if you want to add per-key LED backlighting to your board. These steps could be difficult as they require soldering SMD parts. Please watch [this video](https://www.youtube.com/watch?v=ofmdmeCW4fY) for a video guide! If you want to skip, you can [jump to the next mandatory section](#usb-port)

1. Now, if we want LED backlighting, we need to solder the MOSFET on Q1. Put a little solder on one of the pads.
![](images/build_guide/14-mosfet-solder.jpg)
1. Using tweezers, hold the MOSFET to the pad, oriented the correct way. Use a soldering iron to make the dot of solder you added heat up. and solder the MOSFET to the board.
![](images/build_guide/15-mosfet-installed.jpg)

    !!! Mandatory
        After this block, steps are mandatory unless otherwise noted!

## Resistors for Backlighting (Optional)

!!! Optional
    This step is optional, and only necessary if you want to add per-key LED backlighting to your board. If you want to skip this, you can [jump to the next mandatory section](#usb-port)

1. Next, we're going to solder the 4.7k resistor needed for per-key LED Backlighting. This is optional!
![](images/build_guide/8-mosfet-resistor.jpg)
   In this image, it's not labeled, but on newer PCBs, the pad is labeled with a note "4.7k"
1. The 4.7k resistor The color bands are "Yellow, Violet, Red, Gold". Solder it on just like the diodes.
![](images/build_guide/9-mosfet-resistor-soldered.jpg)
1. Solder all the 61 resistors on, using the same technique practiced on the diodes. Orientation doesn't matter. You don't have to save the resistor legs.
![](images/build_guide/10-resistors.jpg)
1. When you're done, your board should look something like this:
![](images/build_guide/11-resistors-finished.jpg)

    !!! Mandatory
        After this block, steps are mandatory unless otherwise noted!
        
## USB Port

1. Next we'll solder the USB port. Insert the USB mini port. Make sure all the pins are through the holes.
![](images/build_guide/12-usb-port.jpg)
1. Solder the USB mini port
![](images/build_guide/13-usb-port-soldered.jpg)


## Reset Switch

!!! Note
    On both the Ortho48 and Ortho60, you have through hole reset switches, so you won't have to do this SMD soldering! Follow the steps analogous to the USB mini port to install the reset switch.

1. Practice60: Now we must solder the SMD reset switch. Put a little solder on one of the pads.
![](images/build_guide/16-reset-switch.jpg)
1. Practice60: Using tweezers, hold the reset switch to the pad, oriented the correct way. Use a soldering iron to make the dot of solder you added heat up, pinning it in place. Solder the reset switch pins to the board.
![](images/build_guide/17-reset-soldered.jpg)
1. On the Ortho60 and Ortho48, insert the angled reset switch into the reset switch spot, and solder like the USB port.


## Blue Pill Headers

!!! Warning
    If you plan on installing your build in a case, you should use low-profile sockets instead of these headers. There is a low profile socket guide available [here](sockets.md). You must use low profile sockets if you want case compatibility! 

1. Next let's put in the headers for our Blue Pill
![](images/build_guide/18-blue-pill-headers.jpg)
1. Use the blue pill to make sure it's aligned! DO NOT SOLDER THE BLUE PILL YET!
![](images/build_guide/19-align-headers.jpg)
1. Flip the board to the front, keeping the headers installed.
![](images/build_guide/20-flip-board.jpg)
1. Solder the headers to the board. You should flush cut them afterwards
![](images/build_guide/21-solder-header.jpg)

## Blue Pill Modifications

!!! Note
    This section assumes that you've purchased a Blue Pill as part of a kit from me, or from my shop. Most blue pills come with extra jumpers soldered. If this is the case for your Blue Pill, please visit [this page](bluepill-mod.md) for detailed instructions on how to modify it.

1. Since our Bluepills do not have boot jumpers, we need to add some wires to set the boot mode. Put a piece of wire or diode leg between the middle BOOT0 pin and the 0 pin.
1. Flip the Bluepill over and solder the wire into the spots.
1. Repeat for the BOOT1 pin, again connecting the middle pin to 0.
1. At the end of this, your Bluepill should look like this:


## Stabilizers
1. Next, we need to install our stabilizers. I recommend [clipping and lubing](https://www.youtube.com/watch?v=cD5Zj-ZgMLA) the stabilizers prior to installation.
![](images/build_guide/27-stabs-installed.jpg)
1. Once the stabs are done, let's put switches in the plate, and the plate on the PCB. Make sure the switch legs make it through the holes. I like starting with the 4 corners. Flip the board to the back, and solder the switches.
![](images/build_guide/28-corner-switches.jpg)

## Switches
1. Finish the rest of the switches following the same strategy.
![](images/build_guide/29-switches-finished.jpg)
1. When the switches are done, the back of the board should look like this.
![](images/build_guide/30-back-finished.jpg)

    !!! Note
        TODO: Install LEDS

## Final Installation
1. Finally, add the blue pill and solder it to the board. Make sure you have it oriented the correct way! Follow the printout on the board.
![](images/build_guide/31-solder-bluepill.jpg)

    !!! Note
        TODO: Assemble Sandwich Case
