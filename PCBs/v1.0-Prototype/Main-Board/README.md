# ARC-164 Main Board — Version 1.0 Prototype

**Last updated: November 8, 2026 at 5:48 AM MST (America/Denver)**

Untested prototype hardware revision; initial public revision dated November 7, 2026.

- Open [the KiCad project](Project/Main%20Board.kicad_pro).
- [Schematic PDF](Schematics/Main-Board-v1.0-Prototype.pdf)
- [Schematic component BOM](Assembly/BOM.csv)
- [Gerber/drill ZIP](Main-Board-v1.0-Prototype-Gerbers.zip)
- [Front preview](Previews/top.png) / [back preview](Previews/bottom.png)
- [Current wiring](../Docs/Wiring.md), [assembly instructions](../Docs/Assembly.md), [additional sockets/headers](../Docs/Additional-Assembly-Parts.md)
- [Known issues](../Docs/Known-Issues.md), [DRC](Checks/DRC.json), [ERC](Checks/ERC.json)

DRC clean with zero unconnected items and no schematic parity issues. D17 was moved before this final reroute. **The 8 mm Sub-Board mounting stack passed my physical test fitting on November 8, 2026**, using a **20 mm screw, a 6 mm-thick nut and two 1 mm-thick washers at each of four mounts**. Assembled electrical testing and the remaining control, cable, and complete-stack checks still need to be completed. All component positions, outlines, holes and routing were preserved during prototype packaging. The two 40-pin interfaces use cables, not direct stacking connectors. Review prototype limitations before ordering.

**The 0.5 mm gaps between the LED digits are still awaiting the STL print and fit test behind the faceplate.** That spacing test is separate from the **8 mm mounting stack, which has passed test fitting**. I’ll print the new mockup at **100% scale**, with **6 mm-tall display bodies**, and keep the STL off GitHub until I’ve checked the fit.

## Version history

- **1.0 Prototype — November 7, 2026:** Initial three-board prototype package. No assembled electrical validation is claimed.
