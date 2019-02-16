# Bluepill Modification

Stock bluepills are quite tall, and interfere with case compatibility. For that reason, we often need to modify the Bluepull to make it as thin as possible.

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
