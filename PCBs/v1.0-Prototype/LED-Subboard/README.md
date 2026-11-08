# ARC-164 LED Subboard — Version 1.0 Prototype

**Last updated: November 8, 2026 at 10:44 AM MST (America/Denver)**

**PCB ordering is on hold: the J20 cable connector does not clear the Main Board.** I need to redesign **both the Main Board and LED Sub Board** to provide enough connector and cable clearance before ordering. I’ll **keep the tested LED positions, 0.75 mm gaps and 6 mm display-body height unchanged** while revising the connector area. The LED alignment and 8 mm mounting-stack fit passed, but the complete assembly does not yet clear the cable connector. I still need to test-fit the revised boards with the actual connector and cable before ordering; assembled electrical testing also remains pending.

**Historical v1.0 files.** Use the [current LED Sub Board v1.1](../../v1.1/LED-Subboard/README.md), which passed physical mockup fitting. The original files below are retained for reference; assembled electrical testing remains pending.

- Open [the KiCad project](Project/LED%20Subboard.kicad_pro).
- [Schematic PDF](Schematics/LED-Subboard-v1.0-Prototype.pdf)
- [Schematic component BOM](Assembly/BOM.csv)
- [Gerber/drill ZIP](LED-Subboard-v1.0-Prototype-Gerbers.zip)
- [Front preview](Previews/top.png) / [back preview](Previews/bottom.png)
- [Current wiring](../Docs/Wiring.md), [assembly instructions](../Docs/Assembly.md), [additional sockets/headers](../Docs/Additional-Assembly-Parts.md)
- [Known issues](../Docs/Known-Issues.md), [DRC](Checks/DRC.json), [ERC](Checks/ERC.json)

DRC clean with zero unconnected items and no schematic parity issues. All component positions, outlines, holes and routing were preserved during prototype packaging. The two 40-pin interfaces use cables, not direct stacking connectors. Review prototype limitations before ordering.

## Mounting

**The LED positions on the v1.1 mockup passed my 100% print and physical alignment test behind the faceplate**, including the **0.75 mm LED gaps**, **6 mm display bodies**, and **8 mm mounting stack**. In the final adjustment, I moved the **channel LEDs 1 mm right** and the **FREQ LEDs 0.5 mm left** from the previous test layout. Each of the four mounts uses a **20 mm screw, a 6 mm-thick nut and two 1 mm washers**. **Assembled electrical testing remains to be done.**

I mount the LED Sub-Board **above the Main Board**, with the **bottom of the Sub-Board facing the top of the Main Board**. I use **four Sub-Board mounts**, each with a **20 mm screw, a 6 mm-thick nut, and two 1 mm-thick washers**, giving **8 mm spacing** between the Main Board and LED Sub-Board. See the [assembly mounting instructions](../Docs/Assembly.md#led-sub-board-mounting).

## Version history

- **1.0 Prototype — November 7, 2026:** Initial three-board prototype package. No assembled electrical validation is claimed.
