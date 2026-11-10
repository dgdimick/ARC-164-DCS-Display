# ARC-164 PCBs

**Last updated: November 9, 2026 at 6:23 PM MST (America/Denver)**

**Main Board v1.2 is published, but it will not work with any currently or previously published LED Sub Board.** I’ve resized the Main Board and am still working on its matching redesigned Sub Board. **The matching new Sub Board files and STL will stay unpublished until I finish the 100% print and fit test and confirm both the channel LED alignment behind the faceplate and J20 connector/cable clearance with Main Board v1.2.** The latest adjustment moves the **channel LEDs up 0.5 mm** and **J20 up 2 mm total across the last two moves**. The channel LEDs retain their previous **0.5 mm leftward adjustment**; the frequency LED positions, **0.75 mm gaps and 6 mm display bodies** are unchanged. **The new Sub Board is waiting on the 100% print, channel LED alignment and J20 clearance checks before publishing.** Please wait for the matching Sub Board and confirmed assembly clearance before ordering a compatible set. Assembled electrical testing remains pending.

The available downloads are **Main Board v1.2** and **Power Driver Board v1.0 Prototype**. **No compatible Sub Board is published yet**; I’m still developing and testing it. The table below links to the available projects and the Sub Board status.

## Current published versions

| Board | Current version | Source, schematic, BOM and fabrication files |
| --- | --- | --- |
| Main Board | **1.2 — requires the matching redesigned Sub Board; incompatible with all published Sub Boards** | [Main Board v1.2 downloads](v1.2/Main-Board/README.md) |
| Power Driver Board | **1.0 Prototype** | [Power Driver Board](v1.0-Prototype/Power-Driver-Board/README.md) |
| LED Sub-Board | **Withdrawn — resized board awaiting 100% print/J20 fit test** | [Status](v1.1/LED-Subboard/README.md) |

[GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype) · [Wiring and pinouts](v1.0-Prototype/Docs/Wiring.md) · [Assembly instructions](v1.0-Prototype/Docs/Assembly.md)

I’ve checked all three designs in KiCad: the board and schematic checks pass, with no unconnected items or mismatched connections. **I haven’t assembled and electrically tested them yet**, so I’m sharing them as prototypes. Please have a look at [what I still need to test](v1.0-Prototype/Docs/Known-Issues.md) before ordering. If you build a set, I’d love to hear how it goes and see your pictures in [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions).

## Matching LED Sub Board — in development

I still need to **finish and test-fit the matching new Sub Board for Main Board v1.2** before publishing its files or STL:

- Print the latest Sub Board mockup at **100%** and fit it with **Main Board v1.2**.
- Check the **channel LED alignment behind the faceplate** after moving both channel LEDs **up 0.5 mm**, retaining their earlier **0.5 mm leftward adjustment**. Keep the frequency LED positions, **0.75 mm gaps and 6 mm display bodies** unchanged.
- Fit the **actual J20 cable connector** after moving J20 **up 2 mm total across the last two moves**, and check the connector housing and cable clearance with both boards mounted together.
- Confirm the fit before publishing the matching Sub Board. **Main Board v1.2 will not work with any older published Sub Board.**

The earlier LED alignment mockup and **8 mm mounting stack** passed test fitting; **the latest resized Sub Board and J20 clearance test are still pending**. Each of the four mounts uses a **20 mm screw, a 6 mm-thick nut and two 1 mm washers**. Assembled electrical testing remains to be done.

[Sub Board status](v1.1/LED-Subboard/README.md) · [Main project work list](../README.md#things-that-need-to-be-completed)

The white displays use six frequency digits spanning **49.35 mm** and two channel digits spanning **15.95 mm**, with **13.75 mm front-face height**.

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
