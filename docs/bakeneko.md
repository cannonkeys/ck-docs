# Bakeneko Build Guide

First make sure we have all the items we'll need.
Each Bakeneko needs

* A PCB
* A Plate
* USB-C Daughterboard
* JST Cable
* 4xM2 screws (For the Daughterboard)
* Hex Key (for the Screws)
* Silicone O-ring
* Clip-in Stabilizers (typically 4x2U and 1x6.25U)
* 4 x Silicone Feet
* Bakeneko Aluminum Case

!!! Note
    You must use clip in stabilizers for the Bakeneko as screw in stabilizers will interfere with the O ring

## PCB Notice
Bakeneko PCBs come preflashed with VIA compatible firmware. But make sure the switch on the back is set to "0". If it is set to "1", your PCB will be stuck in the failsafe flashing mode.

## Building a Bakeneko
1. Starting Kit:
![](images/bakeneko/01-kit.jpg)
(Unfortunately, the o-ring and silicone feet did not make it into this photo)
1. To help protect the painted finish: flip the keyboard over and install the 4 feet into the indents on the bottom of the case.
![](images/bakeneko/28-install-feet.jpg)


### Installing the Daughterboard
1. We are going to add the daughterboard to the case. Check out your daughterboard and look at how the pins are aligned. Here, they are closer to the top.
![](images/bakeneko/02-daughterboard.jpg)
1. Check out your JST cable, and make sure the holes will align with the daughterboard pins.
![](images/bakeneko/03-jstcable.jpg)
1. Insert the JST cable into the daughterboard, keeping in mind the holes of the cable need to align with the pins on the DB.
![](images/bakeneko/04-jstindb.jpg)
1. Using the 4 M2 screws and hex key, screw the daughterboard into the Bakeneko case. Set the case/DB assembly aside.
![](images/bakeneko/05-db-installed.jpg)

### Preparing your Stabilizers

!!! Note
    If you've never prepared stabilizers before, it may be easier to watch a [video guide](https://www.youtube.com/watch?v=usNx1_d0HbQ) on stabilizers before continuing. We always recommend clipping and lubing stabilizers before using them in a build!

1. Align your stabilizer stem so that the portion with 2 holes is facing outwards.
![](images/bakeneko/06-stab-stem.jpg)
1. The 2 holes in the stem will face out of this hole in the housing.
![](images/bakeneko/07-stab-housing.jpg)
1. Put the stem in the housing. Notice how you can see both holes here. (Or rather - the little plastic piece separating the holes)
![](images/bakeneko/08-stem-in-housing.jpg)
1. Insert the stab wire into the bottom hole and clip the wire into the stabilizer housing. If you're having trouble with this step, watch the video linked above!
![](images/bakeneko/09-wire-clipped.jpg)
1. Repeat the process for the other side and finish assembling your stabilizer.
![](images/bakeneko/10-stab-assembled.jpg)
1. Repeat the process for all of the other stabilizers. (Note: The red stuff you see is lube)
![](images/bakeneko/11-all-stabs.jpg)

### Preparing the PCB/Plate Assembly
1. Install all the stabilizers into the PCB. The front of the stabilizer should go into the larger holes, allowing the back to clip into the smaller ones.
![](images/bakeneko/12-stabs-installed.jpg)
1. Add the plate to the assembly. It should fit easily over the stabilizers.
![](images/bakeneko/13-add-plate.jpg)
1. Now we are going to add switches to our PCB. Ensure our switch pins are straight.
![](images/bakeneko/14-straight-pins.jpg)
1. Align the switch pins with the holes of the hotswap socket in the PCB. Press straight down to install the switch. Be sure the hotswap socket is supported from below to avoid any potential breakage.
![](images/bakeneko/15-align-pins.jpg)

!!! Note
    Be sure to support the hotswap socket from below when installing switches! CannonKeys will not be responsible for damages that occur if this is not done.

5. When installed, the switch will look like this:
![](images/bakeneko/16-switch-installed.jpg)
6. Finish installing the rest of the switches:
![](images/bakeneko/17-all-switches.jpg)

### Installing the O-ring
1. Now we'll install the O-ring. Follow these visual steps. The o ring is stretchy so don't be afraid to stretch it!
![](images/bakeneko/18-oring-start.jpg)
![](images/bakeneko/19-oring-align.jpg)
![](images/bakeneko/20-oring-stretch.jpg)
![](images/bakeneko/21-oring-installed.jpg)

### Connecting the PCB

!!! Note
    Be careful here! JST connectors can sometimes be delicate, so use caution and be sure not to break it off your PCB! CannonKeys will not be responsible for damages that occur due to forces applied to your JST connector!

1. Now we need to connect the PCB to the daughterboard. Ensuring that the JST cable is aligned with the JST connector on the PCB, insert the cable into the connector.
![](images/bakeneko/22-jst-pcb.jpg)
1. Flip the PCB over horizontally to orient it properly. Be sure not to cause any stress to the JST cable or connectors as you do this.
![](images/bakeneko/23-pcb-flip.jpg)
![](images/bakeneko/24-post-flip.jpg)
1. Tuck the JST cable under the PCB
![](images/bakeneko/25-jst-tuck.jpg)

### Final Assembly
1. Tuck the o-ring into the inside of the case. You may need to apply some downward pressure in order to do this. The o-ring uses friction to hold the PCB/Plate assembly in.
![](images/bakeneko/26-oring-tucked.jpg)
1. Push the PCB/Plate assembly down. You should feel some of the O-ring friction as you do this. It will end up resting on the posts in the case.
![](images/bakeneko/27-pushed-down.jpg)
1. Add keycaps and ENJOY!
![](images/bakeneko/29-add-keycaps.jpg)

## Backspace Fix
For some of the early Bakeneko PCBs, "Delete" is mapped to the "Backspace" key. Here is how to easily fix it using [VIA Configurator](https://caniusevia.com)

1. Open VIA. It will look like this:
![](images/bakeneko/via_default.png)
2. Using the Layout tab, toggle on "Split Backspace":
![](images/bakeneko/via_split_layout.png)
3. Go back to the keymap tab, and map "Delete" to "Backspace"
![](images/bakeneko/via_remap.png)
4. Backspace is now fixed!
![](images/bakeneko/via_bs_fixed.png)

## Spacebar Fix
For some of the Bakeneko PCBs (db60), there is an issue in rebinding the spacebar within [VIA](https://caniusevia.com). Here is the fix for the issue.

1. Download the [.json](https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/the-via/keyboards/blob/master/src/cannonkeys/db60/db60.json)
2. Open the file in a text editor, and change every occurrence of `4,5` to `4,6`
![](images/bakeneko/space-fix-editor.png)
3. Save the document, and open Via.
4. Once in via, go to the design tab. Click the load button, and open the .json you just saved.
![](images/bakeneko/space-fix-load.png)
5. Once loaded, your screen should show the keyboard matrix like this.
![](images/bakeneko/space-fix-preview.png)
6. Once that is done, click on the configurator tab on the top left of VIA. You should now be able to edit your keymap as you wish.
![](images/bakeneko/space-fix-final.png)
