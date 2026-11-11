# ARC-164 Main Board — Version 1.2

**Last updated: November 10, 2026 at 5:45 PM MST (America/Denver)**

**LED Sub Board v1.2 is now published for Main Board v1.2.** I printed the latest mockup at **100%** and it passed the fit test, including **frequency and channel LED alignment and J20 connector/cable clearance**. The final layout keeps the **FREQ LEDs up 0.5 mm**, the **channel LEDs up 0.5 mm with their earlier 0.5 mm leftward adjustment**, and **J20 up 2 mm total** from the previous mounting position. The **0.75 mm gaps, 6 mm display bodies and tested 8 mm mounting stack** remain unchanged. **Use Main Board v1.2 with LED Sub Board v1.2; older Sub Boards do not match this Main Board. Assembled electrical testing is still pending.**

## Downloads

- [Complete Main Board v1.2 package](Main-Board-v1.2.zip)
- [KiCad project](Project/Main%20Board.kicad_pro)
- [Schematic PDF](Schematics/Main-Board-v1.2.pdf)
- [Component BOM](Assembly/BOM.csv)
- [Gerber and drill ZIP](Main-Board-v1.2-Gerbers.zip)
- [Main Board print mockup — 100% scale](STLs/ARC-164_Main_Board_v1.2_100pct.stl)
- [DRC and schematic parity report](Checks/DRC.rpt) · [ERC report](Checks/ERC.rpt)

I’ve resized this Main Board and moved the Sub Board mounting holes to match the new layout. The silkscreen and PCB/schematic revision fields identify **v1.2**. This release contains only the Main Board; it does not include the unfinished matching Sub Board.

I moved **J10 to my chosen position**, aligned **SW12 (LOAD/reed) and SW13 (TEST DISPLAY)** below R4, and updated the routing and ground fills. Their matching solder pads now line up horizontally. All other component positions, the outline and mounting holes are unchanged from my latest saved layout.

Fresh KiCad checks report **zero DRC violations, zero unconnected items, zero schematic parity issues and zero ERC violations under the saved project settings**. Disabled checks are listed in the reports. These checks do not prove physical cable clearance or assembled electrical operation. The two 40-pin interfaces use cables, not direct stacking connectors.

## Mounting and compatibility

**Use Main Board v1.2 with the matching LED Sub Board v1.2.** The latest Sub Board mockup passed my **100% print and fit test on November 10, 2026**, including LED alignment and J20 connector/cable clearance. Older Sub Boards do not match Main Board v1.2. Assembled electrical testing remains pending. [Sub Board v1.2 downloads](../LED-Subboard/README.md).

The previously tested Sub Board mounting stack is **8 mm**: each of four mounts uses a **20 mm screw, 6 mm-thick nut and two 1 mm washers**. Panel-to-Main-Board spacing is currently **13.5 mm**; I may use **14 mm** to recess the displays slightly from the glass, subject to the real PCB fit. The Power Driver Board remains at v1.0 Prototype and mounts below Main, components facing down, on **10 standoffs longer than 20 mm**.

[Assembly notes](../../v1.0-Prototype/Docs/Assembly.md) · [Wiring and pinouts](../../v1.0-Prototype/Docs/Wiring.md)

## Version history

- **1.2 — November 9, 2026:** New J10 position, aligned SW12/SW13 solder pads, updated routing and ground fills, and v1.2 PCB/schematic revision markings. The matching Sub Board was not yet published at this release; it was published as v1.2 on November 10 after the physical fit test. Assembled electrical testing remains pending.
- [1.1 — November 9, 2026](../../v1.1/Main-Board/README.md): Resized Main Board and updated mounting holes; superseded by v1.2.
- **1.0 Prototype — November 7, 2026:** Initial publication, subsequently withdrawn.

[PCB overview](../../README.md)
