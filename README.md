# HP Compaq IPAQ G750 Keyboard Bluetooth Adapter
-----------

![Demo of G750 keyboard](/images/demo.gif)

This project makes a Bluetooth adapter for the G750 foldable keyboard. This keyboard was meant to use with vintage PDAs (Windows CE, Palm, Clie etc.). It was sold under various brands (HP, Compaq, Dell, Treo etc.) and has multiple model numbers (G750, G740, G7L0, G7L1, etc.). But as long as they have the same key layout, this adapter should work for them.

Note that there are two variations of the electrical characteristics: G750 uses inverted-TTL for its RX line, while G740, G7L0, G7L1 uses TTL level. Some keyboards also have an extra key at the left side of the space bar. See the [protocol analysis and keycodes](g750_protocol.md) for details.

The G750 keyboard uses an distinctive folding mechanism that slides out to both sides, while the middle piece raises up to the same level. A connector is prop’ed up to provide connectivity to the PDA. This project achieved Bluetooth functionality by replacing that connector module with a custom designed Bluetooth module.

G750 protocol analysis
-----------

[Protocol analysis and keycodes](g750_protocol.md)

Instruction to make the adapter
-----------

[Tutorial for making the adapter](how_to_make.md)

Instruction to install the adapter
-----------

[Tutorial for installing the adapter into the keyboard](install.md)

