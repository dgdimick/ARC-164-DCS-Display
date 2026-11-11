# ARC-164 PCBs

**Last updated: November 10, 2026 at 5:45 PM MST (America/Denver)**

**LED Sub Board v1.2 is now published for Main Board v1.2.** I printed the latest mockup at **100%** and it passed the fit test, including **frequency and channel LED alignment and J20 connector/cable clearance**. The final layout keeps the **FREQ LEDs up 0.5 mm**, the **channel LEDs up 0.5 mm with their earlier 0.5 mm leftward adjustment**, and **J20 up 2 mm total** from the previous mounting position. The **0.75 mm gaps, 6 mm display bodies and tested 8 mm mounting stack** remain unchanged. **Use Main Board v1.2 with LED Sub Board v1.2; older Sub Boards do not match this Main Board. Assembled electrical testing is still pending.**

The available downloads are the matched **Main Board v1.2 and LED Sub Board v1.2**, plus **Power Driver Board v1.0 Prototype**. The Sub Board mockup passed physical fit testing; manufactured-board electrical testing remains pending.

## Current published versions

| Board | Current version | Source, schematic, BOM and fabrication files |
| --- | --- | --- |
| Main Board | **1.2 — use with LED Sub Board v1.2** | [Main Board v1.2 downloads](v1.2/Main-Board/README.md) |
| Power Driver Board | **1.0 Prototype** | [Power Driver Board](v1.0-Prototype/Power-Driver-Board/README.md) |
| LED Sub-Board | **1.2 — physical mockup fit passed; electrical testing pending** | [Sub Board v1.2 downloads](v1.2/LED-Subboard/README.md) |

[GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype) · [Wiring and pinouts](v1.0-Prototype/Docs/Wiring.md) · [Assembly instructions](v1.0-Prototype/Docs/Assembly.md)

I’ve checked all three designs in KiCad: the board and schematic checks pass, with no unconnected items or mismatched connections. **I haven’t assembled and electrically tested them yet**, so I’m sharing them as prototypes. Please have a look at [what I still need to test](v1.0-Prototype/Docs/Known-Issues.md) before ordering. If you build a set, I’d love to hear how it goes and see your pictures in [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions).

## LED Sub Board v1.2 — physical fit passed

**LED Sub Board v1.2 is now published for Main Board v1.2.** I printed the latest mockup at **100%** and it passed the fit test, including **frequency and channel LED alignment and J20 connector/cable clearance**. The final layout keeps the **FREQ LEDs up 0.5 mm**, the **channel LEDs up 0.5 mm with their earlier 0.5 mm leftward adjustment**, and **J20 up 2 mm total** from the previous mounting position. The **0.75 mm gaps, 6 mm display bodies and tested 8 mm mounting stack** remain unchanged. **Use Main Board v1.2 with LED Sub Board v1.2; older Sub Boards do not match this Main Board. Assembled electrical testing is still pending.**

[Sub Board v1.2 downloads and tested STL](v1.2/LED-Subboard/README.md). The six frequency digits span **49.35 mm**, the channel pair spans **15.95 mm**, and the digit bodies are **13.75 mm high across their front faces**.

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
