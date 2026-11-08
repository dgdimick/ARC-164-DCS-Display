# ARC-164 LED Subboard — Version 1.0 Prototype

**Last updated: November 8, 2026 at 7:34 AM MST (America/Denver)**

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

**The 8 mm Sub-Board mounting stack passed my physical test fitting on November 8, 2026.** Each of the **four mounts** uses a **20 mm screw, a 6 mm-thick nut and two 1 mm-thick washers**. The display bodies extend **6 mm above the LED Sub-Board**. **LED Sub-Board v1.1 — in development:** I’ve already changed the version marking on the local board to **v1.1**. This will be the next LED Sub-Board version when finished; it is still awaiting the LED mockup print and fit test. **Version 1.0 Prototype remains the current published download.** I moved the **six FREQ LEDs 1 mm right** and the **two upper channel LEDs 2 mm left** from the previous 0.75 mm-gap layout. Both groups retain **0.75 mm gaps**, and the display bodies remain **6 mm above the PCB**. **The new STL is still awaiting the 100% print and fit test behind the faceplate**, and I’ll keep it off GitHub until I’ve tested it. The **8 mm mounting stack has already passed test fitting**. Assembled electrical testing remains to be done.

I mount the LED Sub-Board **above the Main Board**, with the **bottom of the Sub-Board facing the top of the Main Board**. I use **four Sub-Board mounts**, each with a **20 mm screw, a 6 mm-thick nut, and two 1 mm-thick washers**, giving **8 mm spacing** between the Main Board and LED Sub-Board. See the [assembly mounting instructions](../Docs/Assembly.md#led-sub-board-mounting).

## Version history

- **1.0 Prototype — November 7, 2026:** Initial three-board prototype package. No assembled electrical validation is claimed.
