# How to make the G750 adapter (CH582F based)

Bill of Materials
----------
- [WCH Micro Kbd board] (you can fabricate it yourself using the gerber file in src/version3_ch582f, or buy one from Tindie (to be stocked).)
- 3-pin JST 1.25mm pitch connector with wires.
- Some thin, flexible wire for the switch connection. I use 30 AWG PVDF insulated single core wire.
- 401225 Li-Po battery 100mAh (4mm x 12mm x 25mm in dimensions).
- One travel limit switch, model No. [KFC-V-511](https://www.aliexpress.com/item/3256802435427161.html). Please use this exact model, because the enclosure is specifically designed around it.
- 3D printed enclosure (stl models are in the 3d_print/ folder).
- One M2 screw, 4mm long.
- Double-sided tape.

3D printed parts
----------------
See the stl files in 3d_print/ folder. It comes in 2 files: the upper cap, the main frame. The upper cap needs to use support to print. The main frame has some support already added, it can be printed directly.

I used Tinkercad to create these models. If you are interested in modifying the 3D models, you can visit this link: https://www.tinkercad.com/things/

![Printed parts before assembly](/images/3d_print.jpg "Printed parts before assembly")

How to make the Bluetooth assembly
-------------------

Solder two 4 cm lenth thin wires to the SW1 pads, and the other ends of wires to the travel limit switch.

![wiring pic](/images/wiring1.jpg)

Cut the JST wire into the following dimension:

![wiring pic](/images/wiring2.jpg)

Then solder them to pad 1, 2, 5, according to the schematic.

![wiring pic](/images/wiring3.jpg)

Solder the positive of the Li-Po battery to pad [BAT+], the negative to pad [BAT-].

Insert the PCB into the main frame like this, run the 3 wires in the tube.

![wiring pic](/images/wiring4.jpg)

Put some super glue and install the switch in the main frame, glue it in-place.

![Glue the switch](/images/glue_switch.jpg)

Use double-sided tape to tape the battery at the follwing location. The space is tight so there is not much room for error.

Put the cap over the main frame. Put in the clips first, then screw in the M2 screw.

![wiring pic](/images/cap.jpg)

Programming
-----------
Follow [this tutorial](https://github.com/pymo/wch_micro_kbd/blob/main/doc/wch_isp_tool.md) to flash the firmware. The firmware can be downloaded from the release page of that github. You need Windows PC to flash the firmware.

How to install the Bluetooth assembly to the keyboard
-----------
Unscrew the 3 screws on the back and 2 screws on the front of the keyboard.
![install pic](/images/install1.jpg)

Remove the cover assembly.
![install pic](/images/install2.jpg)

Remove the connector assembly from the cover assembly, unplug the 3-pin plug.
![install pic](/images/install3.jpg)

Put in the Bluetooth assembly into the cover assembly, plug-in the 3-pin plug, make sure all the pins are properly connected.
![install pic](/images/install4.jpg)

Put back the cover assembly.
![install pic](/images/install5.jpg)

Screw the 5 screws.
![install pic](/images/finished.jpg)


Features and quirks
---------------------
- As with any device using Li-Po battery, don't discharge the battery to a very low state. Please charge the battery as soon as you see the red LED blinks. Otherwise the battery health may be affected.

