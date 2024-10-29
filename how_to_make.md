# How to make the G750 adapter (CH582F based)

Bill of Materials
----------
- [WCH Micro Kbd board](https://github.com/pymo/wch_micro_kbd/), you can fabricate it yourself using the gerber file in [my other repo](https://github.com/pymo/wch_micro_kbd/tree/main/pcb/), or buy one from Tindie (will stock after the design is finalized).
- 3-pin JST 1.25mm pitch connector with wires.
- Some thin, flexible wire for the switch connection. I use 30 AWG PVDF insulated single core wire.
- 401225 Li-Po battery 100mAh (4mm x 12mm x 25mm in dimensions).
- One travel limit switch, model No. [KFC-V-511](https://www.aliexpress.com/item/3256802435427161.html). Please use this exact model, because the enclosure is specifically designed around it.
- 3D printed enclosure (stl models are in the 3d_print/ folder).
- One M2 screw, 4mm long.
- Double-sided tape.

3D printed parts
----------------
See the stl files in 3d_print/ folder. It comes in 2 files: the upper cap, the main frame. The upper cap needs to use support to print. The main frame has some support already added, it can be printed directly. PLA filament is recommended, because it is more rigid.

I used TinkerCAD to create these models. If you are interested in modifying the 3D model, you can visit this link: https://www.tinkercad.com/things/e2wjntFVclj-g750-keyboard-adapter

![Printed parts before assembly](/images/3d_print.jpg "Printed parts before assembly")

How to make the Bluetooth assembly
-------------------

Solder two 4 cm length thin wires to the SW1 pads, and the other ends of wires to the travel limit switch.

![wiring pic](/images/wiring1.jpg)

Cut the JST wire into the following dimension, the length is different for G750 (inverted TTL level) and other variants (TTL level):

![wiring pic](/images/wiring2.jpg)

Then solder the JST wire to the PCB (the color of the wire may vary, what's important is the order of the wire at the connector):
 - For G750 (inverted TTL level), solder VCC to pad 1, RXD to pad 2, GND to pad 5
 - For other variants (TTL level), solder VCC to pad 1, RXD to pad 6, GND to pad 5.

![wiring pic](/images/wiring3.jpg)

Solder the positive of the Li-Po battery to pad [BAT+], the negative to pad [BAT-].

Insert the PCB into the main frame like this, run the 3 wires in the tube.

![wiring pic](/images/wiring4.jpg)

Put some super glue and install the switch in the main frame, glue it in-place.

![wiring pic](/images/glue_switch.jpg)

Use double-sided tape to tape the battery at the following location. The upper edge of the battery should align with the upper edge of the PCB.

![Glue the switch](/images/wiring5.jpg)

Put the cap over the main frame. Put in the clips first, then screw in the M2 screw.

![wiring pic](/images/cap.jpg)

Programming
-----------
Follow [this tutorial](https://github.com/pymo/wch_micro_kbd/blob/main/doc/wch_isp_tool.md) to flash the firmware. The firmware can be downloaded from the release page of that Github. You need Windows PC to flash the firmware.

