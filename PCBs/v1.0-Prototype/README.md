# ARC-164 PCB Version 1.0 — Prototype

**Last updated: November 10, 2026 at 5:45 PM MST (America/Denver)**

**LED Sub Board v1.2 is now published for Main Board v1.2.** I printed the latest mockup at **100%** and it passed the fit test, including **frequency and channel LED alignment and J20 connector/cable clearance**. The final layout keeps the **FREQ LEDs up 0.5 mm**, the **channel LEDs up 0.5 mm with their earlier 0.5 mm leftward adjustment**, and **J20 up 2 mm total** from the previous mounting position. The **0.75 mm gaps, 6 mm display bodies and tested 8 mm mounting stack** remain unchanged. **Use Main Board v1.2 with LED Sub Board v1.2; older Sub Boards do not match this Main Board. Assembled electrical testing is still pending.**

Initial public three-board PCB prototype revision, November 7, 2026. These are untested prototypes, not assembled or production-validated hardware. [GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype).

| Board | Source | Fabrication data | Schematic | BOM |
| --- | --- | --- | --- | --- |
| Main Board v1.0 | Withdrawn; [current Main Board v1.2](../v1.2/Main-Board/README.md) uses the [matching Sub Board v1.2](../v1.2/LED-Subboard/README.md) | — | — | — |
| Power Driver Board | [KiCad project](Power-Driver-Board/Project/Power%20Driver%20Board.kicad_pro) | [Gerbers and drills](Power-Driver-Board/Manufacturing/) | [PDF](Power-Driver-Board/Schematics/Power-Driver-Board-v1.0-Prototype.pdf) | [CSV](Power-Driver-Board/Assembly/BOM.csv) |
| LED Subboard v1.0 | Withdrawn; use [Sub Board v1.2](../v1.2/LED-Subboard/README.md) with Main Board v1.2 | — | — | — |

Open the project in KiCad 10.0.7 or newer. Each project includes its used footprint libraries, custom symbols and all referenced 3D models with project-relative paths. BOMs are schematic-generated component lists; sockets, Teensy headers and cables are additional assembly items described in the documentation.

## Required reading

- [Current three-board wiring, all cable pinouts and Teensy GPIO mapping](Docs/Wiring.md)
- [Assembly order and orientation checks](Docs/Assembly.md)
- [Known issues and validation limits](Docs/Known-Issues.md)
- [Electrical connector audit](Docs/Electrical-Audit.json)
- [Connector comparison](Docs/Connector-Pin-Comparison.csv)

## Prototype limitations

**At the original v1.0 release, all three boards had zero DRC violations, zero unconnected items, and zero schematic parity issues; all three schematics passed ERC.** These historical checks do not establish compatibility with Main Board v1.2 or validate the unfinished matching Sub Board. D17 was moved clear of SW7’s courtyard, and Main Board routing and both GND fills were rebuilt. Library warnings and D12 silkscreen clipping were corrected without moving components, outlines or holes.

All manufactured-board electrical tests, actual cable/connector fit, socket/stack clearance and firmware integration remain to be performed. Review these limits before ordering. Use the supplied board version as a prototype baseline; this is not a production sign-off.

The manufacturing folders contain two-layer Gerbers (front/back copper, solder mask and silkscreen, plus Edge.Cuts) and separate plated/non-plated Excellon drill files where applicable. Routed holes/cutouts remain in Edge.Cuts; oblong strain-relief slots are included in drill data. Board thickness is recorded in each KiCad project. Confirm the manufacturer’s preview before ordering.

See the included project licenses. The models retain their source provenance; standard KiCad assets follow their library licenses.
