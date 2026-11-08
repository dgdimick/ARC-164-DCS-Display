# ARC-164 PCB Version 1.0 — Prototype

**Last updated: November 8, 2026 at 12:03 PM MST (America/Denver)**

**Main Board and LED Sub Board downloads are temporarily withdrawn; please don’t order these boards yet.** I’ve resized both boards to address the **J20 cable connector clearance**, keeping the tested **LED positions, 0.75 mm gaps and 6 mm display bodies unchanged**. Both new mockups are waiting on **100% print and fit testing together with the actual J20 cable connector**. I’ll provide replacement board files after checking the fit. The earlier LED alignment and **8 mm Sub Board mounting stack** passed their tests, but clearance of the resized assembly is not yet confirmed. The new Main Board and Sub Board STLs are staying off GitHub until I’ve tested them.

Initial public three-board PCB prototype revision, November 7, 2026. These are untested prototypes, not assembled or production-validated hardware. [GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype).

| Board | Source | Fabrication data | Schematic | BOM |
| --- | --- | --- | --- | --- |
| Main Board | Downloads withdrawn pending resized-board and J20 fit testing | — | — | — |
| Power Driver Board | [KiCad project](Power-Driver-Board/Project/Power%20Driver%20Board.kicad_pro) | [Gerbers and drills](Power-Driver-Board/Manufacturing/) | [PDF](Power-Driver-Board/Schematics/Power-Driver-Board-v1.0-Prototype.pdf) | [CSV](Power-Driver-Board/Assembly/BOM.csv) |
| LED Subboard | Downloads withdrawn pending resized-board and J20 fit testing | — | — | — |

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
