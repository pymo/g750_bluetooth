# HP Compaq IPAQ G750 Keyboard Bluetooth Adapter

![Demo of G750 keyboard](/images/demo.gif)

This project makes a Bluetooth adapter for the G750 foldable keyboard. This keyboard was meant to use with vintage PDAs (Windows CE, Palm, Clie etc.). It was sold under various brands (HP, Compaq, Dell, Treo etc.) and has multiple model numbers (G750, G740, G7L0, G7L1, etc.). But as long as they have the same look, this adapter should work for them.

Note that there are two variants of the electrical characteristics: G750 uses inverted-TTL for its RX line, while G740, G7L0, G7L1 uses TTL level. Some keyboards also have an extra key at the left side of the space bar. See the [protocol analysis and keycodes](g750_protocol.md) for details. Therefore, the hardware wiring and the firmware are slightly different for different models.

The G750 keyboard uses an distinctive folding mechanism that slides out to both sides, while the middle piece raises up to the same level. A connector is prop’ed up to provide connectivity to the PDA. This project achieved Bluetooth functionality by replacing that connector module with a custom designed Bluetooth module.

Where to buy
-----------

The keyboard itself can be found on eBay for around $15 to $20. You can search using the keywords "G750", "G740", "G700", "G7L0" or "G7L1" + "Keyboard".

About the adapter, if you don't want to build it yourself, I've made a few of them for sale at Tindie. [https://www.tindie.com/products/36279/](https://www.tindie.com/products/36279/)

G750 protocol analysis
-----------

[Protocol analysis and keycodes](g750_protocol.md)

Instruction to make the adapter
-----------

[Tutorial for making the adapter](how_to_make.md)

Instruction to install the adapter
-----------

[Tutorial for installing the adapter into the keyboard](install.md)

PCB design and firmware
-----------
These are in a [separate repo](https://github.com/pymo/wch_micro_kbd/), the PCB design is shared with the Palm Portable Keyboard Bluetooth mod.

Demo on Youtube
-----------

[![G750 Keyboard demo](http://img.youtube.com/vi/qPznzD5e45k/0.jpg)](https://www.youtube.com/watch?v=a8__Df5YKs4 "Converting the G750 folding keyboard into Bluetooth")


