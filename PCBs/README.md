# ARC-164 PCBs

**Last updated: November 8, 2026 at 7:34 AM MST (America/Denver)**

I’ve shared the first prototype versions of all three boards below. The downloads include the KiCad projects and the files you can send to a PCB manufacturer, along with the wiring and assembly notes I’m putting together as I build mine.

## Current published versions

| Board | Current version | Source, schematic, BOM and fabrication files |
| --- | --- | --- |
| Main Board | **1.0 Prototype** | [Main Board](v1.0-Prototype/Main-Board/README.md) |
| Power Driver Board | **1.0 Prototype** | [Power Driver Board](v1.0-Prototype/Power-Driver-Board/README.md) |
| LED Sub-Board | **1.0 Prototype** | [LED Sub-Board](v1.0-Prototype/LED-Subboard/README.md) |

[Download all three boards](https://github.com/dgdimick/ARC-164-DCS-Display/releases/download/pcb-v1.0-prototype/ARC-164-PCBs-v1.0-Prototype.zip) · [GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype) · [Wiring and pinouts](v1.0-Prototype/Docs/Wiring.md) · [Assembly instructions](v1.0-Prototype/Docs/Assembly.md)

I’ve checked all three designs in KiCad: the board and schematic checks pass, with no unconnected items or mismatched connections. **I haven’t assembled and electrically tested them yet**, so I’m sharing them as prototypes. Please have a look at [what I still need to test](v1.0-Prototype/Docs/Known-Issues.md) before ordering. If you build a set, I’d love to hear how it goes and see your pictures in [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions).

## LED Sub-Board v1.1 — in development

I’ve adjusted my local LED Sub-Board for the **QBSLDIW301GR white displays**, with **six frequency digits spanning 49.35 mm** and **two channel digits spanning 15.95 mm**. The front faces measure **13.75 mm high**, and the display bodies extend **6 mm above the PCB**. **The 8 mm Sub-Board mounting stack has passed physical test fitting behind the faceplate.**

The new spacing is a local revision and is not included in the Version 1.0 prototype downloads linked above. See my [current display plan](../README.md#seven-segment-display-plan).

**The 8 mm Sub-Board mounting stack passed my physical test fitting on November 8, 2026.** Each of the **four mounts** uses a **20 mm screw, a 6 mm-thick nut and two 1 mm-thick washers**. The display bodies extend **6 mm above the LED Sub-Board**. **LED Sub-Board v1.1 — in development:** I’ve already changed the version marking on the local board to **v1.1**. This will be the next LED Sub-Board version when finished; it is still awaiting the LED mockup print and fit test. **Version 1.0 Prototype remains the current published download.** I moved the **six FREQ LEDs 1 mm right** and the **two upper channel LEDs 2 mm left** from the previous 0.75 mm-gap layout. Both groups retain **0.75 mm gaps**, and the display bodies remain **6 mm above the PCB**. **The new STL is still awaiting the 100% print and fit test behind the faceplate**, and I’ll keep it off GitHub until I’ve tested it. The **8 mm mounting stack has already passed test fitting**. Assembled electrical testing remains to be done.

## Panel-to-Main-Board spacing

I use **18 mm total spacing between the panel and Main Board**, made up of a **3 mm-thick nut plus a 15 mm standoff** at each mounting point. See the [assembly instructions](v1.0-Prototype/Docs/Assembly.md#panel-to-main-board-mounting) for the mounting notes.

The **LED Sub-Board mounts above the Main Board**, with its bottom connected to the Main Board’s top. The mounting stack gives **8 mm total spacing**.

I use **four Sub-Board mounts**, each with a **20 mm screw, a 6 mm-thick nut, and two 1 mm-thick washers**, giving **8 mm spacing** between the Main Board and LED Sub-Board.

The **Power Driver Board mounts below the Main Board using 10 standoffs, each longer than 20 mm, with its components facing down**. The exact length can vary to clear components, sockets, Teensy headers, and cables.

## Three-board design

- **Main Board:** Five FREQ encoders, Channel/VOL encoders, MAIN/PRESET direct-contact rotary switches, wired-switch pads, and 19 green backlight LEDs with resistors.
- **Power Driver Board:** Teensy 4.1, two MAX7219 display drivers, 74AHCT125 buffer, backlight MOSFET, regulated-5V input jack, and inter-board connectors.
- **LED Sub-Board:** Six SC36-11SURKWA frequency digits and two preset digits, connected by a 40-pin cable.

I’m building the five-frequency-encoder version first. I may come back to the frequency rotary-switch version later; the [main README](../README.md#frequency-controls) explains that plan.

[Back to the main README](../README.md)
