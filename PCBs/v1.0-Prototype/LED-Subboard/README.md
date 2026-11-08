# ARC-164 LED Subboard — Version 1.0 Prototype

**Last updated: November 8, 2026 at 5:18 AM MST (America/Denver)**

Untested prototype hardware revision; initial public revision dated November 7, 2026.

- Open [the KiCad project](Project/LED%20Subboard.kicad_pro).
- [Schematic PDF](Schematics/LED-Subboard-v1.0-Prototype.pdf)
- [Schematic component BOM](Assembly/BOM.csv)
- [Gerber/drill ZIP](LED-Subboard-v1.0-Prototype-Gerbers.zip)
- [Front preview](Previews/top.png) / [back preview](Previews/bottom.png)
- [Current wiring](../Docs/Wiring.md), [assembly instructions](../Docs/Assembly.md), [additional sockets/headers](../Docs/Additional-Assembly-Parts.md)
- [Known issues](../Docs/Known-Issues.md), [DRC](Checks/DRC.json), [ERC](Checks/ERC.json)

DRC clean with zero unconnected items and no schematic parity issues. All component positions, outlines, holes and routing were preserved during prototype packaging. The two 40-pin interfaces use cables, not direct stacking connectors. Review prototype limitations before ordering.

## Mounting

**The display bodies extend 6 mm above the LED Sub-Board. I’m using 8 mm Main-Board-to-Sub-Board spacing, with a 20 mm screw, a 6 mm-thick nut and two 1 mm-thick washers at each of the four mounts, pending the fit test.** I’ll print the corrected 6 mm display mockup at **100% scale** and check it behind the faceplate before confirming the mounting stack or publishing the STL.

I mount the LED Sub-Board **above the Main Board**, with the **bottom of the Sub-Board facing the top of the Main Board**. I use **four Sub-Board mounts**, each with a **20 mm screw, a 6 mm-thick nut, and two 1 mm-thick washers**, giving **8 mm spacing** between the Main Board and LED Sub-Board. See the [assembly mounting instructions](../Docs/Assembly.md#led-sub-board-mounting).

## Version history

- **1.0 Prototype — November 7, 2026:** Initial three-board prototype package. No assembled electrical validation is claimed.
