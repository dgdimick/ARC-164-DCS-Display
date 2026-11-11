# ARC-164 Power Driver Board — Version 1.0 Prototype

**Last updated: November 10, 2026 at 5:45 PM MST (America/Denver)**

**LED Sub Board v1.2 is now published for Main Board v1.2.** I printed the latest mockup at **100%** and it passed the fit test, including **frequency and channel LED alignment and J20 connector/cable clearance**. The final layout keeps the **FREQ LEDs up 0.5 mm**, the **channel LEDs up 0.5 mm with their earlier 0.5 mm leftward adjustment**, and **J20 up 2 mm total** from the previous mounting position. The **0.75 mm gaps, 6 mm display bodies and tested 8 mm mounting stack** remain unchanged. **Use Main Board v1.2 with LED Sub Board v1.2; older Sub Boards do not match this Main Board. Assembled electrical testing is still pending.**

Untested prototype hardware revision; initial public revision dated November 7, 2026.

**Use Main Board v1.2 with the matching LED Sub Board v1.2.** The latest Sub Board mockup passed my **100% print and fit test on November 10, 2026**, including LED alignment and J20 connector/cable clearance. Older Sub Boards do not match Main Board v1.2. Assembled electrical testing remains pending.

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
