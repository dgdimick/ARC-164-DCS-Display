# ARC-164 Power Driver Board — Version 1.0 Prototype

**Last updated: November 9, 2026 at 4:41 PM MST (America/Denver)**

The latest Sub Board mockup moves both channel LEDs **0.5 mm left from the previous mockup**, with the frequency LED positions, **0.75 mm gaps and 6 mm display bodies** unchanged. **The 100% print, channel LED alignment and J20 connector/cable-clearance checks with Main Board v1.1 are still pending before I publish the new Sub Board files or STL.**

Untested prototype hardware revision; initial public revision dated November 7, 2026.

**Main Board v1.1 will not work with any older published Sub Board.** I’m still developing the matching new Sub Board; its files and STL remain unpublished while I check the channel LED alignment and J20 cable clearance. Please wait for the matching version before ordering or assembling a board set. See the [current PCB compatibility status](../../README.md).

- Open [the KiCad project](Project/Power%20Driver%20Board.kicad_pro).
- [Schematic PDF](Schematics/Power-Driver-Board-v1.0-Prototype.pdf)
- [Schematic component BOM](Assembly/BOM.csv)
- [Gerber/drill ZIP](Power-Driver-Board-v1.0-Prototype-Gerbers.zip)
- [Front preview](Previews/top.png) / [back preview](Previews/bottom.png)
- [Current wiring](../Docs/Wiring.md), [assembly instructions](../Docs/Assembly.md), [additional sockets/headers](../Docs/Additional-Assembly-Parts.md)
- [Known issues](../Docs/Known-Issues.md), [DRC](Checks/DRC.json), [ERC](Checks/ERC.json)

DRC clean with zero unconnected items and no schematic parity issues. All component positions, outlines, holes and routing were preserved during prototype packaging. The two 40-pin interfaces use cables, not direct stacking connectors. Review prototype limitations before ordering.

## Mounting

I mount the Power Driver Board **below the Main Board with its components facing down**, away from the Main Board. Use **10 standoffs, each longer than 20 mm**; the exact length can vary to provide clearance for components, sockets, Teensy headers, and cables. See the [assembly mounting instructions](../Docs/Assembly.md#power-driver-board-mounting).

## Version history

- **1.0 Prototype — November 7, 2026:** Initial three-board prototype package. No assembled electrical validation is claimed.
