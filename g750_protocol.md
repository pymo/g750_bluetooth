# G750 reverse engineering

The G750 keyboard and its variants use a three-wire serial protocol. After disassembling the connector module, you can see a JST 3-pin, 1.25mm pitch male header. The 3 wires are:

- Ground

- RXD (Serial data)
  - For G750, the voltage is RS232 level (or more precisely, invert-TTL level, where 0V is 1 and 3.3V is 0)
  - For G740, G7L0 and G7L1, the voltage is TTL level (0V is 0 and 3.3V is 1)

- VCC, I tested with 3.3v and it works.

![Schematic](/images/schematic.jpg "Schematic")


After the keyboard is supplied with VCC, when a key is pressed or released, it sends a 2-byte key-code over the serial wire. The baud rate is 4800n1. Let’s denote the two bytes as Byte1 and Byte2:

 - The most significant bit of Byte1 denotes the state of the key: 0 is pressed, 1 is released

 - The remaining 7-bit of Byte1 is the scancode, see the following table for the mapping

 - Byte2 is the inversion of Byte1’s 7-bit scancode. i.e. (Byte1 | 0b01111111) XOR Byte2 = 0b11111111. I think it is for error detection. In practice we can ignore this byte and only look at the scancode in Byte1.

Scancode table
----------

G750 with US layout:

| Scan code | HID code | Scan code | HID code | Scan code | HID code | Scan code | HID code |
| :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: | :-------: |
| 0x02 | HID_KEY_FN | 0x28 | HID_KEY_ARROW_UP | 0x43 | HID_KEY_I | 0x60 | HID_KEY_ARROW_DOWN |
| 0x07 | HID_KEY_GUI_LEFT | 0x2A | HID_KEY_V | 0x44 | HID_KEY_O | 0x66 | HID_KEY_DELETE |
| 0x0D | HID_KEY_TAB | 0x2B | HID_KEY_F | 0x45 | HID_KEY_0 | 0x71 | HID_KEY_BACKSPACE |
| 0x0E | HID_KEY_GRAVE | 0x2C | HID_KEY_T | 0x46 | HID_KEY_9 | 0x73 | HID_KEY_CONTROL_RIGHT |
| 0x11 | HID_KEY_ALT_RIGHT | 0x2D | HID_KEY_R | 0x49 | HID_KEY_PERIOD |  | |
| 0x12 | HID_KEY_SHIFT_LEFT | 0x2E | HID_KEY_5 | 0x4A | HID_KEY_SLASH |  | |
| 0x14 | HID_KEY_CONTROL_LEFT | 0x2F | HID_KEY_ARROW_RIGHT | 0x4B | HID_KEY_L |  | | 
| 0x15 | HID_KEY_Q | 0x31 | HID_KEY_N | 0x4C | HID_KEY_SEMICOLON |  | |
| 0x16 | HID_KEY_1 | 0x32 | HID_KEY_B | 0x4D | HID_KEY_P |  | |
| 0x1A | HID_KEY_Z | 0x33 | HID_KEY_H | 0x4E | HID_KEY_MINUS |  | | 
| 0x1B | HID_KEY_S | 0x34 | HID_KEY_G | 0x52 | HID_KEY_APOSTROPHE |  | | 
| 0x1C | HID_KEY_A | 0x35 | HID_KEY_Y | 0x54 | HID_KEY_BRACKET_LEFT | | | 
| 0x1D | HID_KEY_W | 0x36 | HID_KEY_6 | 0x55 | HID_KEY_EQUAL |  | |
| 0x1E | HID_KEY_2 | 0x3A | HID_KEY_M | 0x58 | HID_KEY_CAPS_LOCK | | | 
| 0x21 | HID_KEY_C | 0x3B | HID_KEY_J | 0x59 | HID_KEY_SHIFT_RIGHT | | | 
| 0x22 | HID_KEY_X | 0x3C | HID_KEY_U | 0x5A | HID_KEY_RETURN |  | |
| 0x23 | HID_KEY_D | 0x3D | HID_KEY_7 | 0x5B | HID_KEY_BRACKET_RIGHT | | | 
| 0x24 | HID_KEY_E | 0x3E | HID_KEY_8 | 0x5C | HID_KEY_SPACE |  | |
| 0x25 | HID_KEY_4 | 0x41 | HID_KEY_COMMA | 0x5D | HID_KEY_BACKSLASH | | | 
| 0x26 | HID_KEY_3 | 0x42 | HID_KEY_K | 0x5E | HID_KEY_ARROW_LEFT | | | 


