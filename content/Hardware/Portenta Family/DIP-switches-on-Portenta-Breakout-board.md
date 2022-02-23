---
title: "DIP switches on Portenta Breakout board"
---

The Arduino Portenta Breakout board makes all high-density connectors individually accessible, making it quick and easy to connect external components and devices to your Portenta family board. The Breakout board comes with 2 DIP switches located on the top side of the board.

![The top side of the Portenta Breakout board, with the DIP switches highlighted.](img/DIP_breakout.png)

## DIP switches on the Portenta H7

The different positions and modes for the Portenta H7 are explained below.

**BOOT_SEL:**

* ON: Keeps the Portenta in Boot mode.
* OFF: Operation mode (default)

**BOOT:**

* ON: Enables the embedded bootloader. Firmware can be upload via the USB port on the breakout board (DFU). USB-A to USB-A (non-crossover) cable required. The Portenta H7 has to be powered through the USB-C connector or VIN.
* OFF: Boots normally (default)

Users must pay special attention to the DIP switches position to ensure the right boot mode is selected before powering the board. If the RESET button does not behave as expected, or you are unable to enter _Bootloader Mode_, you should verify the DIP switch configuration.

**For the standard operation mode both DIP switches must be set to OFF**. To do so, simply position the white switches next to "1" and "2" respectively (opposite the "ON" label printed on the switch connector itself).