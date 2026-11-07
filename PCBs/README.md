# ARC-164 PCBs

**Last updated: November 7, 2026 at 12:12 PM MST (America/Denver)**

## Current published versions

| Board | Current version | Source, schematic, BOM and fabrication files |
| --- | --- | --- |
| Main Board | **1.0 Prototype** | [Main Board](v1.0-Prototype/Main-Board/README.md) |
| Power Driver Board | **1.0 Prototype** | [Power Driver Board](v1.0-Prototype/Power-Driver-Board/README.md) |
| LED Sub-Board | **1.0 Prototype** | [LED Sub-Board](v1.0-Prototype/LED-Subboard/README.md) |

[Download all three boards](https://github.com/dgdimick/ARC-164-DCS-Display/releases/download/pcb-v1.0-prototype/ARC-164-PCBs-v1.0-Prototype.zip) · [GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype) · [Wiring and pinouts](v1.0-Prototype/Docs/Wiring.md) · [Assembly instructions](v1.0-Prototype/Docs/Assembly.md)

All three boards pass DRC/ERC with zero unconnected items and no schematic parity issues. These are **untested prototypes**, with assembled electrical tests, physical stack/socket/cable checks and firmware integration still outstanding. Read the [validation limits](v1.0-Prototype/Docs/Known-Issues.md) before ordering.

## Three-board design

- **Main Board:** Five FREQ encoders, Channel/VOL encoders, MAIN/PRESET direct-contact rotary switches, wired-switch pads, and 19 green backlight LEDs with resistors.
- **Power Driver Board:** Teensy 4.1, two MAX7219 display drivers, 74AHCT125 buffer, backlight MOSFET, regulated-5V input jack, and inter-board connectors.
- **LED Sub-Board:** Six SC36-11SURKWA frequency digits and two preset digits, connected by a 40-pin cable.

The five-frequency-encoder design is the current baseline. The alternative frequency rotary-switch design remains a future plan; see the [main README](../README.md#frequency-controls).

[Back to the main README](../README.md)
