<img alt="Tierwriter Logo" src="https://github.com/jyuenger/Tierwriter/blob/main/Miscellaneous/Logo.png" width=480>

A tiered, typewriter-inspired, handwired 60% mechanical keyboard with arrows, 7u/8u spacebar, dual MX/Alps support, Pi 4 mounting holes, and modified ISO layout

## Renders
<img src="https://github.com/jyuenger/Tierwriter/blob/main/Miscellaneous/Renders/01.png" width=200> <img src="https://github.com/jyuenger/Tierwriter/blob/main/Miscellaneous/Renders/05.png" width=200> <img src="https://github.com/jyuenger/Tierwriter/blob/main/Miscellaneous/Renders/02.png" width=200>

See [Parts List](#what-you'll-need)

Jump to [Build Guide](#build-guide)

# Introduction

Ever want a keyboard that's actually tiered, like an old-school typewriter, so that each row sits slightly above the row in front of it? Not being able to find anything like this, I set out to design my own. Despite the complexity of the build, this is a very basic, no-frills board. No LEDs, no layers, no fuss. (Though you're welcome to modify it to include all of these things.)

The design principles were to keep it close-ish to a vintage typewriter in terms of the layout, and to accommodate (but not require) vintage parts. So it sports a [60% layout with a minimalist bottom row](https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Build%20Guide%20Illustrations/Default%20Keymap.png), big spacebar, and small mods squished out to the edges of the board. It can use vintage Alps switches (with the provided Alps/MX combo plates), and fit a spacebar up to 8u long. 

The internal space created by the tiers gave me the idea to support mounting a Raspberry Pi 4 inside.

I'm normally a UK ISO user. While the Enter key here can't span two rows, there are alpha keys for hash, grave/negation, and non-US backslash (on row 1), as well as an ISO left Shift. For other langauges that use ISO layout, the 1u R4 Caps Lock key can be remapped as an additional alpha.

Finally, there are arrow keys. I can't live without dedicated arrow keys.

*** WARNING: This is a VERY bouncy typing experience. ***

Default Keymap

<img alt="Default keymap" src="https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Build%20Guide%20Illustrations/Default%20Keymap.png" width=480>

# What You'll Need:
- A controller ([Stampy RP2040](https://keeb.io/products/stampy-rp2040-usb-c-controller-board-for-handwiring)) and firmware (UF2 files in the Firmware/QMK and Firmware/VIAL folders)
- Five custom 1.5mm thick aluminum switchplates, one for each row (AI files for lasercutting in the Plates/MX and Plates/ALPS-MX Combo folders)
- The Rear and Side Assembly (STL file for 3D printing in the STLs folder)
- Ten M2.5 10mm screws (six more if you want to screw the Rear and Side Assembly to the base plate for mounting a Pi)
- Ten M2.5 threaded inserts (six more if you want to screw the Rear and Side Assembly to the base plate for mounting a Pi)
- An MX or Alps keycap set with the following ***nonstandard keys***: 1.5u R2 backspace, 1.5u R3 Enter. You'll also need a 7U or 8U spacebar, and any extra 1u R4 key that you'd like to use as a Caps Lock
- 70 MX or Alps switches
- 70 1N4148 through-hole diodes
- Insulated wire for connecting the key matrix to the controller (see matrix/pin diagram in the Documentation/Wiring folder)
- Solder and soldering iron (for wiring, and for heat-setting the threaded inserts into the support wedges)
- One clip-in plate mounted 7u or 8u stabilizer for the spacebar ([8U stabilizers available at SPRiT](https://www.spritdesigns.com/product-page/stabilizers))

## Optional Parts

- ***Recommended***: 70 [1u Amoeba PCBs](https://keeb.io/products/amoeba-single-switch-pcbs), ([Ameoba wiring instructions here](https://github.com/mtl/keyboard-pcbs/blob/master/svg/instructions.svg)). These will work with MX or Alps switches. The build guide assumes you're using these
- Five decorative 1.5-3mm thick acrylic top plates, one for each row (AI files for lasercutting in the Plates/Tops folder; will fit MX or Alps build)
- 3mm thick base plate for mounting a Pi 4 (AI file for lasercutting in the Plates/Bottom Plate folder)
- Four M2.5 screws for mounting the Pi 4

You'll have a few leftover switches, diodes, and Amoebas; the 70 count factors in spares.

# Build Guide

## Caveats

These instructions assume you're using [Amoeba 1u PCBs](https://keeb.io/products/amoeba-single-switch-pcbs) on every key, a [Stampy RP2040 PCB](https://keeb.io/products/stampy-rp2040-usb-c-controller-board-for-handwiring). and through-hole diodes. Minor changes will be necessary if not, but the basics of the build should remain the same. Note that you can use the Amoebas with Alps switches as well as MX!

## Attaching and Soldering Diodes

1. On each Amoeba, insert a 1N4148 through-hole diode into underside in the [indicated location](https://github.com/mtl/keyboard-pcbs/blob/master/svg/instructions.svg), with the diode's black bar on the same side as the bar printed on the Amoeba.
2. Solder both ends of the diode onto the Amoeba, and trim the diode's legs if necessary.

<img alt="Through hole diodes inserted into a row of Amoebas"  src="https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Build%20Guide%20Illustrations/Diodes.png" width="480">

## Assembling the Switchplates

1. On the far left end of the row 1 switchplate, insert three switches into the holes, and then attach the Stampy PCB underneath them, with the USB connector facing north. Solder the Stampy to the three switches (Esc, 1, and 2).

<img alt="Stampy mounted under the Esc/1/2 keys on row 0" src="https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Build%20Guide%20Illustrations/Controller.png" width="480">

2. Continue inserting switches into the remaining holes on row 1, and do the same for rows 2-4.

<img alt="Switches mounted in plate" src="https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Build%20Guide%20Illustrations/Switches.png" width="480">

3. Attach Amoeba PCBs to the underside of each switch in rows 1-4 (except the ones soldered to the Stampy), and solder the switches to their individual Amoebas. You may need to break the Amoebas into individual 1u boards if leaving them together warps the plate.
4. For Row 5, clip in the 7u or 8u stabilizer first, then insert the spacebar switch into the switchplate's spacebar hole. Insert the remaining switches, and attach and solder the Amoeba PCBs underneath each.

## Building the Rear and Side Assembly

1. Using a soldering iron, heat set a threaded insert into each screw hole on the upper side of the Rear and Side Assembly.
2. If you're attaching the optional base plate, also heat set threaded inserts into the screw holes on the flat underwide of the assembly.

The assembly, with mounting holes for the row plates.

<img alt="Side and rear assembly" src="https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Build%20Guide%20Illustrations/Assembly.png" width="480">


## Row Wiring

1. For each switchplate, [solder the Amoeba PCBs together into a row.](https://github.com/mtl/keyboard-pcbs/blob/master/svg/instructions.svg). (Ignore the switches soldered into the Stampy.)

<img alt="Row 0 wiring" src="https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Build%20Guide%20Illustrations/Row0.png" width="480">

## Attaching Rows to the Rear and Side Assembly

1. Screw in each row's switchplate into the appropriate tier on the Rear and Side Assembly. Row 1 will be on the highest tier (the farthest back from you), with the USB port on the Stampy facing away from you, though the notch in the rear wall. Rows 2 and 3 are identical. Row 5 will be closest to you, on the lowest tier.
2. Optionally, place the decorative top plates on top of each switchplate before screwing them to the assembly.

## Column Wiring

1. [Solder the columns of the Amoebas together](https://github.com/mtl/keyboard-pcbs/blob/master/svg/instructions.svg), creating 15 soldered columns (ignoring the three switches on the Stampy). The Grave key at the end of Row 1, opposite the Stampy, is its own column, and won't be soldered to any other keys in this step. [Consult the wiring diagram](https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Wiring/Stampy%20RP2040%20Matrix%20Wiring.png) to make sure each column runs between rows correctly.

## Wiring the Row and Column Matrix to the Stampy PCB

1. Using the [wiring diagram](https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Wiring/Stampy%20RP2040%20Matrix%20Wiring.png) as a guide, solder the end of each row and column to its appropriate IO pin on the Stampy. Row 0 will be GP14, and columns 0-2 will be GP11, GP10, and GP15 respectively. (These assignments are built into the Stampy.)

<img alt="Stampy RP2040 schematic" src="https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Wiring/Stampy.png" width=480>

## Flashing the Firmware

1. Connect the Stampy to your computer using its USB-C port.
2. Press and hold the reset button on the Stampy for one second, and release.
3. Your OS should mount the Stampy as a drive.
4. Drag either the UF2 QMK or VIAL firmware file (located here under Firmware/QMK or Firmware/VIAL) onto the Stampy's drive.
5. The Stampy will reset itself. Test the keys to make sure each key is working properly, according to the [default layout diagram](https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Build%20Guide%20Illustrations/Default%20Keymap.png).

## Editing the Keymap

1. If you've flashed the board with the VIAL firmware, just plug the board in, launch VIAL, and it should immediately be recognized and display a live keymap of the current layout. The default layout is barebones, but you can use VIAL to add additional layers, and change any key's behavior on the fly.
2. For QMK, you'll need to modify keymap.c and recompile the firmware.

## Attaching the Optional Base

1. Turn the completed keyboard over gently, so the caps are facing down, and you're looking directly at the underside, with the threaded inserts facing towards you.
2. Align the screw slots in the bottom plate with the assembly's threaded inserts, and install the screws in each to connect them.


The base plate, with Pi mounting holes in the left rear

<img alt="Base plate" src="https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Build%20Guide%20Illustrations/Base.png" width="480">


3. You can mount a Raspberry Pi 4 in the open area in the rear left, using M2.5 screws. The Pi's USB ports should face to the left of the board during normal usage, with the power and HDMI ports facing the rear.
4. Use a short USB-C to USB-A cable to connect the keyboard's USB port to one of the Pi's.
