# ARC-164 PCBs

**Last updated: November 8, 2026 at 12:52 AM MST (America/Denver)**

I’ve shared the first prototype versions of all three boards below. The downloads include the KiCad projects and the files you can send to a PCB manufacturer, along with the wiring and assembly notes I’m putting together as I build mine.

## Current published versions

| Board | Current version | Source, schematic, BOM and fabrication files |
| --- | --- | --- |
| Main Board | **1.0 Prototype** | [Main Board](v1.0-Prototype/Main-Board/README.md) |
| Power Driver Board | **1.0 Prototype** | [Power Driver Board](v1.0-Prototype/Power-Driver-Board/README.md) |
| LED Sub-Board | **1.0 Prototype** | [LED Sub-Board](v1.0-Prototype/LED-Subboard/README.md) |

[Download all three boards](https://github.com/dgdimick/ARC-164-DCS-Display/releases/download/pcb-v1.0-prototype/ARC-164-PCBs-v1.0-Prototype.zip) · [GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype) · [Wiring and pinouts](v1.0-Prototype/Docs/Wiring.md) · [Assembly instructions](v1.0-Prototype/Docs/Assembly.md)

I’ve checked all three designs in KiCad: the board and schematic checks pass, with no unconnected items or mismatched connections. **I haven’t assembled and electrically tested them yet**, so I’m sharing them as prototypes. Please have a look at [what I still need to test](v1.0-Prototype/Docs/Known-Issues.md) before ordering. If you build a set, I’d love to hear how it goes and see your pictures in [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions).

## New display spacing — fit test pending

I’ve adjusted my local LED Sub-Board for the **QBSLDIW301GR white displays**, with **six frequency digits spanning 46.5 mm** and **two channel digits spanning 15.3 mm**. The measured display bodies are **13.75 mm tall**. **The new LED spacing still needs to be checked behind the faceplate.**

I’ll print the new display-board mockup at **100% scale** and check both windows, mounting-hole alignment, height, and clearance around the controls and other boards. **I’ll wait to publish the STL until I’ve tested the fit.** The new spacing is a local revision and is not included in the Version 1.0 prototype downloads linked above. See my [current display plan](../README.md#seven-segment-display-plan).

## Three-board design

- **Main Board:** Five FREQ encoders, Channel/VOL encoders, MAIN/PRESET direct-contact rotary switches, wired-switch pads, and 19 green backlight LEDs with resistors.
- **Power Driver Board:** Teensy 4.1, two MAX7219 display drivers, 74AHCT125 buffer, backlight MOSFET, regulated-5V input jack, and inter-board connectors.
- **LED Sub-Board:** Six SC36-11SURKWA frequency digits and two preset digits, connected by a 40-pin cable.

I’m building the five-frequency-encoder version first. I may come back to the frequency rotary-switch version later; the [main README](../README.md#frequency-controls) explains that plan.

[Back to the main README](../README.md)
