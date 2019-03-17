# Bluepill Modification

Stock bluepills are quite tall, and interfere with case compatibility. For that reason, we often need to modify the Bluepull to make it as thin as possible.

## With Jumpers

If your blue pill has yellow jumpers soldered on it:

1. We're going to modify our Blue Pill to make it as thin as possible. We need to add a boot jumper so we can get rid of the existing ones.
![](images/build_guide/22-modify-blue-pill.jpg)
1. We want to connect the two pins shown. Use a diode leg to do it.
![](images/build_guide/23-diode-leg-blue-pill.jpg)
1. Solder it to the middle pin first, then the outer pin.
![](images/build_guide/24-jumper-soldered.jpg)
1. Repeat for the other side and cut off the excess. Your blue pill should look like this.
![](images/build_guide/25-blue-pill-modified.jpg)
1. Now we can cut off all the boot jumpers. I also desoldered the reset switch since we have one on our board, but you don't have to.
![](images/build_guide/26-cut-boot-jumper.jpg)

## Without Jumpers

If your blue pill does not have yellow jumpers on it:

1. Since our Bluepills do not have boot jumpers, we need to add some wires to set the boot mode. 
![](images/build_guide/m01-starting-bluepill.jpg)
1. Put a piece of wire or diode leg between the middle BOOT0 pin and the 0 pin.
![](images/build_guide/m02-wire-bluepill.jpg)
1. Flip the Bluepill over and solder the wire into the spots.
![](images/build_guide/m03-soldered-bluepill.jpg)
1. Repeat for the BOOT1 pin, again connecting the middle pin to 0.
![](images/build_guide/m04-repeat-bluepill.jpg)
1. Cut the extra wire/diode legs off the back of your blue pill.
![](images/build_guide/m05-cut-pins-bluepill.jpg)
1. At the end of this, your Bluepill should look like this:
![](images/build_guide/m06-finished-bluepill.jpg)