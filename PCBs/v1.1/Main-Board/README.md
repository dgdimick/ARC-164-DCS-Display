# ARC-164 Main Board — Version 1.1

**Last updated: November 9, 2026 at 3:30 PM MST (America/Denver)**

**Main Board v1.1 is published, but it will not work with any currently or previously published LED Sub Board.** I’ve resized the Main Board and am still working on its matching redesigned Sub Board. **The matching new Sub Board files and STL will stay unpublished until I finish the 100% print and fit test and confirm both the channel LED alignment behind the faceplate and J20 connector/cable clearance with Main Board v1.1.** I’m keeping the frequency LED positions and **0.75 mm gaps** unchanged; the channel LEDs’ latest **1 mm move right** still needs its alignment check. Please wait for the matching Sub Board and confirmed assembly clearance before ordering a compatible set. Assembled electrical testing remains pending.

## Downloads

- [Complete Main Board v1.1 package](Main-Board-v1.1.zip)
- [KiCad project](Project/Main%20Board.kicad_pro)
- [Schematic PDF](Schematics/Main-Board-v1.1.pdf)
- [Component BOM](Assembly/BOM.csv)
- [Gerber and drill ZIP](Main-Board-v1.1-Gerbers.zip)
- [Main Board print mockup — 100% scale](STLs/ARC-164_Main_Board_v1.1_100pct.stl)
- [DRC and schematic parity report](Checks/DRC.rpt) · [ERC report](Checks/ERC.rpt)

I’ve resized this Main Board and moved the Sub Board mounting holes to match the new layout. The silkscreen and PCB/schematic revision fields identify **v1.1**. This release contains only the Main Board; it does not include the unfinished matching Sub Board.

Fresh KiCad checks report **zero DRC violations, zero unconnected items, zero schematic parity issues and zero ERC violations under the saved project settings**. Disabled checks are listed in the reports. These checks do not prove physical cable clearance or assembled electrical operation. The two 40-pin interfaces use cables, not direct stacking connectors.

## Mounting and compatibility

**Do not combine Main Board v1.1 with any older published Sub Board.** I’m still checking the matching resized Sub Board and actual J20 cable connector together. The current local Sub Board mockup has the channel LEDs shifted another **1 mm right**, with the frequency LEDs unchanged, **0.75 mm gaps** and **6 mm display bodies**. It is not part of this download.

The previously tested Sub Board mounting stack is **8 mm**: each of four mounts uses a **20 mm screw, 6 mm-thick nut and two 1 mm washers**. Panel-to-Main-Board spacing is currently **13.5 mm**; I may use **14 mm** to recess the displays slightly from the glass, subject to the real PCB fit. The Power Driver Board remains at v1.0 Prototype and mounts below Main, components facing down, on **10 standoffs longer than 20 mm**.

[Assembly notes](../../v1.0-Prototype/Docs/Assembly.md) · [Wiring and pinouts](../../v1.0-Prototype/Docs/Wiring.md)

## Version history

- **1.1 — November 9, 2026:** Resized Main Board and updated mounting holes; requires the matching new Sub Board. Electrical assembly testing remains pending.
- **1.0 Prototype — November 7, 2026:** Initial publication, subsequently withdrawn.

[PCB overview](../../README.md)
