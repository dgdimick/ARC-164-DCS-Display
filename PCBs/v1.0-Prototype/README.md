# ARC-164 PCB Version 1.0 — Prototype

**Last updated: November 7, 2026 at 12:12 PM MST (America/Denver)**

Initial public three-board PCB prototype revision, November 7, 2026. These are untested prototypes, not assembled or production-validated hardware. [GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype).

| Board | Source | Fabrication data | Schematic | BOM |
| --- | --- | --- | --- | --- |
| Main Board | [KiCad project](Main-Board/Project/Main%20Board.kicad_pro) | [Gerbers and drills](Main-Board/Manufacturing/) | [PDF](Main-Board/Schematics/Main-Board-v1.0-Prototype.pdf) | [CSV](Main-Board/Assembly/BOM.csv) |
| Power Driver Board | [KiCad project](Power-Driver-Board/Project/Power%20Driver%20Board.kicad_pro) | [Gerbers and drills](Power-Driver-Board/Manufacturing/) | [PDF](Power-Driver-Board/Schematics/Power-Driver-Board-v1.0-Prototype.pdf) | [CSV](Power-Driver-Board/Assembly/BOM.csv) |
| LED Subboard | [KiCad project](LED-Subboard/Project/LED%20Subboard.kicad_pro) | [Gerbers and drills](LED-Subboard/Manufacturing/) | [PDF](LED-Subboard/Schematics/LED-Subboard-v1.0-Prototype.pdf) | [CSV](LED-Subboard/Assembly/BOM.csv) |

Open the project in KiCad 10.0.7 or newer. Each project includes its used footprint libraries, custom symbols and all referenced 3D models with project-relative paths. BOMs are schematic-generated component lists; sockets, Teensy headers and cables are additional assembly items described in the documentation.

## Required reading

- [Current three-board wiring, all cable pinouts and Teensy GPIO mapping](Docs/Wiring.md)
- [Assembly order and orientation checks](Docs/Assembly.md)
- [Known issues and validation limits](Docs/Known-Issues.md)
- [Electrical connector audit](Docs/Electrical-Audit.json)
- [Connector comparison](Docs/Connector-Pin-Comparison.csv)

## Prototype limitations

**All three boards now have zero DRC violations, zero unconnected items, and zero schematic parity issues; all three schematics pass ERC.** D17 was moved clear of SW7’s courtyard, and Main Board routing and both GND fills were rebuilt. Library warnings and D12 silkscreen clipping were corrected without moving components, outlines or holes.

All manufactured-board electrical tests, actual cable/connector fit, socket/stack clearance and firmware integration remain to be performed. Review these limits before ordering. Use the supplied board version as a prototype baseline; this is not a production sign-off.

The manufacturing folders contain two-layer Gerbers (front/back copper, solder mask and silkscreen, plus Edge.Cuts) and separate plated/non-plated Excellon drill files where applicable. Routed holes/cutouts remain in Edge.Cuts; oblong strain-relief slots are included in drill data. Board thickness is recorded in each KiCad project. Confirm the manufacturer’s preview before ordering.

See the included project licenses. The models retain their source provenance; standard KiCad assets follow their library licenses.
