# ARC-164 Main Board — Version 1.1

**Last updated: November 10, 2026 at 5:45 PM MST (America/Denver)**

**Superseded by [Main Board v1.2](../../v1.2/Main-Board/README.md).** This v1.1 page and download are retained as historical reference. The current matched pair is Main Board v1.2 and Sub Board v1.2; this old Main Board is historical.

**Use Main Board v1.2 with the matching LED Sub Board v1.2.** The latest Sub Board mockup passed my **100% print and fit test on November 10, 2026**, including LED alignment and J20 connector/cable clearance. Older Sub Boards do not match Main Board v1.2. Assembled electrical testing remains pending.

## Downloads

- [Complete Main Board v1.1 package](Main-Board-v1.1.zip)
- [KiCad project](Project/Main%20Board.kicad_pro)
- [Schematic PDF](Schematics/Main-Board-v1.1.pdf)
- [Component BOM](Assembly/BOM.csv)
- [Gerber and drill ZIP](Main-Board-v1.1-Gerbers.zip)
- [Main Board print mockup — 100% scale](STLs/ARC-164_Main_Board_v1.1_100pct.stl)
- [DRC and schematic parity report](Checks/DRC.rpt) · [ERC report](Checks/ERC.rpt)

I’ve resized this Main Board and moved the Sub Board mounting holes to match the new layout. The silkscreen and PCB/schematic revision fields identify **v1.1**. This release contains only the Main Board; it does not include the unfinished matching Sub Board.

I placed **J10 slightly off-center on Main Board v1.1** to leave room in case I need to make changes later.

Fresh KiCad checks report **zero DRC violations, zero unconnected items, zero schematic parity issues and zero ERC violations under the saved project settings**. Disabled checks are listed in the reports. These checks do not prove physical cable clearance or assembled electrical operation. The two 40-pin interfaces use cables, not direct stacking connectors.

## Mounting and compatibility

This Main Board v1.1 is retained as historical reference. Use the current matched **Main Board v1.2 and Sub Board v1.2**; the Sub Board v1.2 mockup passed physical fitting on November 10, 2026. That test does not establish compatibility with this older Main Board. Assembled electrical testing remains pending.

The previously tested Sub Board mounting stack is **8 mm**: each of four mounts uses a **20 mm screw, 6 mm-thick nut and two 1 mm washers**. Panel-to-Main-Board spacing is currently **13.5 mm**; I may use **14 mm** to recess the displays slightly from the glass, subject to the real PCB fit. The Power Driver Board remains at v1.0 Prototype and mounts below Main, components facing down, on **10 standoffs longer than 20 mm**.

[Assembly notes](../../v1.0-Prototype/Docs/Assembly.md) · [Wiring and pinouts](../../v1.0-Prototype/Docs/Wiring.md)

## Version history

- **1.1 — November 9, 2026:** Resized Main Board and updated mounting holes; requires the matching new Sub Board. Electrical assembly testing remains pending.
- **1.0 Prototype — November 7, 2026:** Initial publication, subsequently withdrawn.

[PCB overview](../../README.md)
