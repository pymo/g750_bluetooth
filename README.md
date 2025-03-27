# HP Compaq IPAQ G750 Keyboard Bluetooth Adapter

![Demo of G750 keyboard](/images/demo.gif)

This project makes a Bluetooth adapter for the G750 foldable keyboard. This keyboard was meant to use with vintage PDAs (Windows CE, Palm, Clie etc.). It was sold under various brands (HP, Compaq, Dell, Treo etc.) and has multiple model numbers (G750, G7L0, G7L1, etc.). But as long as they have the same look, this adapter should work for them.

There are one exception: G700 for Toshiba, it uses USB protocol instead of serial, so it can not be supported. (There is also a G700 for Palm and Sony Clie, maybe that can be supported, but I haven't tested it yet.)

Note that there are two variants of the electrical characteristics: G750 uses inverted-TTL for its RX line, while G7L0, G7L1 uses TTL level. Some keyboards also have one or two extra keys depending on the layout and the PDA's OS. See the [protocol analysis and keycodes](g750_protocol.md) for details. Therefore, the hardware wiring and the firmware are slightly different for different models.

The G750 keyboard uses an distinctive folding mechanism that slides out to both sides, while the middle piece raises up to the same level. A connector is prop’ed up to provide connectivity to the PDA. This project achieved Bluetooth functionality by replacing that connector module with a custom designed Bluetooth module.

Support status
-----------

| Brand | Model | Supported | logic level |
| :-------: | :-------: | :-------: | :-------: |
| HP | G750 | Yes | inverted TTL |
| Compaq | 249711-001 | Yes | inverted TTL |
| ViewSonic | PPC-KYB-001 | Yes | inverted TTL |
| Dell | G7L0 or G7L1 | Yes | TTL |
| Treo | G740 | Yes | TTL |
| Belkin | G700 for Toshiba | No | USB protocol |
| Belkin | G700 for Palm/Clie | ? | Not tested |

Where to buy
-----------

The keyboard itself can be found on eBay for around $15 to $20. You can search using the keywords "G750", "249711-001", "G7L0" or "G7L1" + "Keyboard". G740 for Treo is not recommended because of its weird layout.

I have a few modded keyboards for sale at [https://www.ebay.com/itm/226602504961](https://www.ebay.com/itm/226602504961)

If you just want the adapter, I've made some for sale at Tindie. [https://www.tindie.com/products/36279/](https://www.tindie.com/products/36279/)

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
These are in a [separate repo](https://github.com/pymo/wch_micro_kbd/), the PCB design is shared with the Palm Portable Keyboard Bluetooth mod. The PCB uses a WCH CH582F chip, which is a RISC V based Bluetooth controller. It is low cost, power efficient and easy enough to use, which is why I chose it.

Spacebar Issue Fix
-----------
It is a known issue that these keyboard's spacebar can't reliably register. But [there is a simple fix for that](spacebar_fix.md).

Demo on Youtube
-----------

[![G750 Keyboard demo](http://img.youtube.com/vi/a8__Df5YKs4/0.jpg)](https://www.youtube.com/watch?v=a8__Df5YKs4 "Converting the G750 folding keyboard into Bluetooth")


