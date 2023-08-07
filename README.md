<img alt="Tierwriter Logo" src="https://github.com/jyuenger/Tierwriter/blob/main/Miscellaneous/Logo.png" width=480>

A tiered, typewriter-inspired, handwired 60% mechanical keyboard with arrows, 7u/8u spacebar, dual MX/Alps support, and modified ISO

## FULL BUILD GUIDE AND PROTOTYPE PHOTOS COMING SEPTEMBER 2023.
See [Parts List](#what-you'll-need)

Jump to [Provisional Build Guide](#provisional-build-guide)

# Introduction

Ever want a keyboard that's actually tiered, like an old-school typewriter, so that each row sits slightly above the row in front of it? Not being able to find anything like this, I set out to design my own. Despite the complexity of the build, this is a very basic, no-frills board. No LEDs, no layers, no fuss. (Though you're welcome to modify it to include all of these things.)

The design principles were to keep it close-ish to a vintage typewriter in terms of the layout, and to accommodate (but not require) vintage parts. So it sports a [60% layout with a minimalist bottom row](https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Build%20Guide%20Illustrations/Default%20Keymap.png), big spacebar, and small mods squished out to the edges of the board. It can use vintage Alps switches (with the provided Alps/MX combo plates), and fit a spacebar up to 8u long. 

I'm normally a UK ISO user. While the Enter key here can't span two rows, there are alpha keys for hash, grave/negation, and non-US backslash (on row 1), as well as an ISO left Shift. For other langauges that use ISO layout, the 1u R4 Caps Lock key can be remapped as an additional alpha.

Finally, there are arrows. I can't live without dedicated arrow keys.

## Illustrations

Exploded parts diagram

<img alt="Exploded parts diagram" src="https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Build%20Guide%20Illustrations/Diagram.png" width="480">

Mockup of tiered structure

<img alt="Mockup of tiered structure" src="https://github.com/jyuenger/Tierwriter/blob/9abbb466a296ae63d2cabd3b20eebf0fafaae6d2/documentation/Mockup.png" width="300"> 

Default Keymap

<img alt="Default keymap" src="https://github.com/jyuenger/Tierwriter/blob/main/Documentation/Build%20Guide%20Illustrations/Default%20Keymap.png" width=480>

# What You'll Need:
- A controller ([Stampy RP2040](https://keeb.io/products/stampy-rp2040-usb-c-controller-board-for-handwiring)) and firmware (UF2 files in the Firmware/QMK and Firmware/VIAL folders)
- Five custom 1.5mm thick aluminum switchplates, one for each row (AI files for lasercutting in the Plates/MX and Plates/ALPS-MX Combo folders)
- Two stepped PLA support wedges (STL file for 3D printing in the STLs folder)
- Ten M3 8mm screws (four more if you want to screw the undersides of the wedges the optional base plate, plus three more if you want to install the optional rear wall)
- Ten M3 threaded inserts to heat-set into the holes in the support wedges (four more if you want to screw the undersides of the wedges the optional base plate, plus three more if you want to install the rear wall)
- An MX or Alps keycap set with the following ***nonstandard keys***: 1.5u R2 backspace, 1.5u R3 Enter. You'll also need a 7U or 8U spacebar, and any extra 1u R4 key that you'd like to use as a Caps Lock
- 70 MX or Alps switches
- 70 1N4148 through-hole diodes
- Insulated wire for connecting the key matrix to the controller (see matrix/pin diagram in the Documentation/Wiring folder)
- Solder and soldering iron (for wiring, and for heat-setting the threaded inserts into the support wedges)
- One clip-in plate mounted 7u or 8u stabilizer for the spacebar ([8U stabilizers available at SPRiT](https://www.spritdesigns.com/product-page/stabilizers))

## Optional Parts

- ***Recommended***: 70 [1u Amoeba PCBs](https://keeb.io/products/amoeba-single-switch-pcbs), ([Ameoba wiring instructions here](https://github.com/mtl/keyboard-pcbs/blob/master/svg/instructions.svg)). These will work with MX or Alps switches. The build guide assumes you're using these
- Five decorative 3mm thick acrylic top plates, one for each row (AI files for lasercutting in the Plates/Tops folder; will fit MX or Alps build)
- 3mm thick acrylic base plate (AI file for lasercutting in the Plates/Bottom Plate folder)
- PLA rear wall (STL file for 3D printing in the STLs folder)
- Outer shell (based upon [a design](https://cults3d.com/en/3d-model/gadget/mini-typewriter-phone-stand) by fresnelTHz) (STL file for 3D pringing in the STLs folder). Note that if you choose to use the outer shell, you must omit the base plate and rear wall to fit.

You'll have a couple leftover switches, diodes, and Amoebas; the 70 count factors in spares.

# Provisional Build Guide

## Caveats

These instructions assume you're using [Amoeba 1u PCBs](https://keeb.io/products/amoeba-single-switch-pcbs) on every key, a [Stampy RP2040 PCB](https://keeb.io/products/stampy-rp2040-usb-c-controller-board-for-handwiring). and through-hole diodes. Minor changes will be necessary if not, but the basics of the build should remain the same. Note that you can use the Amoebas with Alps switches as well as MX!

## Attaching and Soldering Diodes

1. On each Amoeba, insert a 1N4148 through-hole diode into underside in the [indicated location](https://github.com/mtl/keyboard-pcbs/blob/master/svg/instructions.svg), with the diode's black bar on the same side as the bar printed on the Amoeba.
2. Solder both ends of the diode onto the Amoeba, and trim the diode's legs if necessary.

## Assembling the Switchplates

1. On the far left end of the row 1 switchplate, insert three switches into the holes, and then attach the Stampy PCB underneath them, with the USB connector facing north. Solder the Stampy to the three switches (Esc, 1, and 2).
2. Continue inserting switches into the remaining holes on row 1, and do the same for rows 2-4.
3. Attach Amoeba PCBs to the underside of each switch in rows 1-4 (except the ones soldered to the Stampy), and solder the switches to their individual Amoebas.
4. For Row 5, clip in the 7u or 8u stabilizer first, then insert the spacebar switch into the switchplate's spacebar hole. Insert the remaining switches, and attach and solder the Amoeba PCBs underneath each.

## Assembling the Tiered Support Wedges

1. Using a soldering iron, heat set a threaded insert into each screw hole on the upper side of both tiered support wedges.
2. If you're attaching the optional base plate, also heat set threaded inserts into the screw holes on the flat underwide of each tiered support wedge.

## Row Wiring

1. For each assembled switchplate, [solder the Amoeba PCBs together horizontally](https://github.com/mtl/keyboard-pcbs/blob/master/svg/instructions.svg) into their rows. (Ignore the switches soldered into the Stampy.)

## Attaching Rows to the Tiered Support Wedges

1. Screw in each row's switchplate into the appropriate tier on each end of the two tiered support wedges. Row 1 will be on the highest tier, the farthest back from you, with the USB port on the Stampy facing away from you. Rows 2 and 3 are identical. Row 5 will be closest to you, on the lowest tier.
2. Optionally, place the decorative top plates on top of each switchplate before screwing them to the support wedges.

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

## Attaching the Optional Base and Rear Wall

1. Disconnect the keyboard, and screw the bottom plate to the two tiered support wedges, with the logo facing down (readable when looking at the underside of the assembled keyboard).
2. Heat set threaded inserts into each of the screw holes on the rear wall.
3. Screw the rear wall to the base plate, between the two tiered support wedges. The notched end should go underneath the Stampy to provide extra room.

## Using the Outer Shell (based on an original design by fresnelTHZ)

Note that the Outer Shell is not compatible with the rear wall and base; omit or remove those if using the outer shell.

Outer casing model originally by [fresnelTHz](https://cults3d.com/en/users/fresnelTHz/3d-models)

Made available under [CC BY](https://creativecommons.org/licenses/by/4.0/) attribution license

1. 3D print the outer shell STL (in the STLs folder).
2. Run a USB-C cable through the hole in the right rear of the outer shell, to the cut-out area in the front.
3. Place the entire Tierwriter assembly (the completed Tierwriter including stepped support wedges and switchplates) partially into the front cavity, so the USB-C cable reaches it.
4. Connect the USB-C cable to the Stampy's USB-C port, and slide the assembly as far back as it will go against the rear wall of the front cavity.
