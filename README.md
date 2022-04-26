# Palm Portable Keyboard Bluetooth Adapter

This project is a DIY bluetooth adapter for the Palm Portable Keyboards (PPK), so you can use it with any phone, tablet or laptop that supports BLE (i.e. Bluetooth 4.0 or later). The cost of the materials are around 15~35 US dollars, depending on which version you build.

Demo on Youtube:

[![Bluetooth Palm Portable Keyboard demo](http://img.youtube.com/vi/o8ccRMmagCI/0.jpg)](http://www.youtube.com/watch?v=o8ccRMmagCI "Converting a Palm Portable Keyboard into a Bluetooth keyboard!
")

[Hackaday blog post](https://hackaday.com/2022/02/08/palm-portable-keyboard-goes-wireless/) about this project.

I've made a small batch of the version 2 adapter for sale. Here is the link to the product: https://www.tindie.com/products/26595/

This project is inspired by [cy384](https://github.com/cy384/ppk_usb)'s USB PPK adapter, and [Christian](https://hackaday.io/project/181800-palm-pilot-keyboard-bluetooth-conversion)'s ESP32-based PPK bluetooth adapter. 

I've made two versions of the adapter: version 1 is based on an Adafruit Feather nRF52840 Express board, version 2 is based on a LilyGo-T-OI-PLUS ESP32-C3 board. Here are the differences of these two versions, you can choose which one to build.

|  version 1  |               version 2                |
| :-------: | :-----------------------------------------------------------------: |
| nRF52840 chip | ESP32-C3 chip |
| $25 for the main board | $5 for the main board |
| Micro-USB charge port | Type-C charge port |
| Only charges when connected to the keyboard | Charges independently |
| more power efficient | less power efficient |
| smaller battery | larger battery |
| more components, harder to solder | less components, easier to solder |
| has a button to forget the pairing | no button, has to forget the pairing on the host side |
| no need to sleep | sleeps after idling for 30 minutes to save power, press any key to wake up |

Both versions work with the Palm III keyboard (black plastic, p/n P10713U) and the Palm V keyboard (dark grey metal, p/n 3C10439). Version 2 also works with Handspring Visor (Targus PA800 or PA800U). Other variants of this keyboard (connectors for Palm M500, HP Jornada, Compaq iPaq PocketPC, or IrDA version etc.) are not supported.

Tutorials to build the adapter
-----------

[How to build the version 1 adapter](version1_tutorial.md)

[How to build the version 2 adapter](version2_tutorial.md)


Special Key mapping
-----------
- Fn+Tab for Esc
- Fn+number keys for F1-F10, Fn+- for F11, Fn+= for F12
- Fn+up for volume up, Fn+down for volume down
- Fn+left for brightness down, and Fn+right for brightness up.
- Fn+Cmd is Homepage key (Home button in iOS).
- Cmd is mapped to super (aka Windows/Apple key).
- Date is mapped to Home, Phone is mapped to End.
- To-Do is mapped to PageUp, Memo is mapped to PageDown.
- Done is mapped to Insert.

Adding to or modifying the mapping is straightforward, just edit the `config_keymap` and `config_fnkeymap` functions.

![Bluetooth Palm Portable Keyboard's stand supporting an iPhone](/images/ppk_demo_iphone.jpg "Bluetooth Palm Portable Keyboard working with a phone")

