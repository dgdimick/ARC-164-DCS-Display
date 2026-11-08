# ARC-164 PCBs

**Last updated: November 8, 2026 at 10:44 AM MST (America/Denver)**

**PCB ordering is on hold: the J20 cable connector does not clear the Main Board.** I need to redesign **both the Main Board and LED Sub Board** to provide enough connector and cable clearance before ordering. I’ll **keep the tested LED positions, 0.75 mm gaps and 6 mm display-body height unchanged** while revising the connector area. The LED alignment and 8 mm mounting-stack fit passed, but the complete assembly does not yet clear the cable connector. I still need to test-fit the revised boards with the actual connector and cable before ordering; assembled electrical testing also remains pending.

I’ve shared the first prototype versions of all three boards below. The downloads include the KiCad projects and the files you can send to a PCB manufacturer, along with the wiring and assembly notes I’m putting together as I build mine.

## Current published versions

| Board | Current version | Source, schematic, BOM and fabrication files |
| --- | --- | --- |
| Main Board | **1.0 Prototype — redesign required; do not order** | [Main Board](v1.0-Prototype/Main-Board/README.md) |
| Power Driver Board | **1.0 Prototype** | [Power Driver Board](v1.0-Prototype/Power-Driver-Board/README.md) |
| LED Sub-Board | **1.1 — LED alignment tested; J20 clearance redesign required; do not order** | [LED Sub-Board](v1.1/LED-Subboard/README.md) |

[Historical v1.0 three-board package](https://github.com/dgdimick/ARC-164-DCS-Display/releases/download/pcb-v1.0-prototype/ARC-164-PCBs-v1.0-Prototype.zip) · [GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype) · [Wiring and pinouts](v1.0-Prototype/Docs/Wiring.md) · [Assembly instructions](v1.0-Prototype/Docs/Assembly.md)

I’ve checked all three designs in KiCad: the board and schematic checks pass, with no unconnected items or mismatched connections. **I haven’t assembled and electrically tested them yet**, so I’m sharing them as prototypes. Please have a look at [what I still need to test](v1.0-Prototype/Docs/Known-Issues.md) before ordering. If you build a set, I’d love to hear how it goes and see your pictures in [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions).

## LED Sub-Board v1.1

**The LED positions on the v1.1 mockup passed my 100% print and physical alignment test behind the faceplate**, including the **0.75 mm LED gaps**, **6 mm display bodies**, and **8 mm mounting stack**. In the final adjustment, I moved the **channel LEDs 1 mm right** and the **FREQ LEDs 0.5 mm left** from the previous test layout. Each of the four mounts uses a **20 mm screw, a 6 mm-thick nut and two 1 mm washers**. **Assembled electrical testing remains to be done.**

[Current v1.1 downloads, Gerbers and tested STL](v1.1/LED-Subboard/README.md). The white displays use six frequency digits spanning **49.35 mm** and two channel digits spanning **15.95 mm**, with **13.75 mm front-face height**.

## Panel-to-Main-Board spacing

I currently have **13.5 mm between the panel and Main Board**. I may use **14 mm** to let the LEDs sit slightly farther back from the glass. I’ll check the spacing when the manufactured PCBs arrive and add an extra spacer if needed. See the [assembly instructions](v1.0-Prototype/Docs/Assembly.md#panel-to-main-board-mounting) for the mounting notes.

The **LED Sub-Board mounts above the Main Board**, with its bottom connected to the Main Board’s top. The mounting stack gives **8 mm total spacing**.

I use **four Sub-Board mounts**, each with a **20 mm screw, a 6 mm-thick nut, and two 1 mm-thick washers**, giving **8 mm spacing** between the Main Board and LED Sub-Board.

The **Power Driver Board mounts below the Main Board using 10 standoffs, each longer than 20 mm, with its components facing down**. The exact length can vary to clear components, sockets, Teensy headers, and cables.

## Three-board design

- **Main Board:** Five FREQ encoders, Channel/VOL encoders, MAIN/PRESET direct-contact rotary switches, wired-switch pads, and 19 green backlight LEDs with resistors.
- **Power Driver Board:** Teensy 4.1, two MAX7219 display drivers, 74AHCT125 buffer, backlight MOSFET, regulated-5V input jack, and inter-board connectors.
- **LED Sub-Board:** Six QBSLDIW301GR white frequency digits and two white preset digits, connected by a 40-pin cable.

I’m building the five-frequency-encoder version first. I may come back to the frequency rotary-switch version later; the [main README](../README.md#frequency-controls) explains that plan.

[Back to the main README](../README.md)
