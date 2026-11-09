# ARC-164 PCB Version 1.0 — Prototype

**Last updated: November 9, 2026 at 4:41 PM MST (America/Denver)**

**Main Board v1.1 is published, but it will not work with any currently or previously published LED Sub Board.** I’ve resized the Main Board and am still working on its matching redesigned Sub Board. **The matching new Sub Board files and STL will stay unpublished until I finish the 100% print and fit test and confirm both the channel LED alignment behind the faceplate and J20 connector/cable clearance with Main Board v1.1.** I’m keeping the frequency LED positions and **0.75 mm gaps** unchanged; the channel LEDs’ latest **0.5 mm move left from the previous mockup** still needs its alignment check. **The 100% print, channel LED alignment and J20 connector/cable-clearance checks remain pending before publication.** Please wait for the matching Sub Board and confirmed assembly clearance before ordering a compatible set. Assembled electrical testing remains pending.

Initial public three-board PCB prototype revision, November 7, 2026. These are untested prototypes, not assembled or production-validated hardware. [GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype).

| Board | Source | Fabrication data | Schematic | BOM |
| --- | --- | --- | --- | --- |
| Main Board v1.0 | Withdrawn; [current Main Board v1.1](../v1.1/Main-Board/README.md) requires a new, unpublished Sub Board | — | — | — |
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

**At the original v1.0 release, all three boards had zero DRC violations, zero unconnected items, and zero schematic parity issues; all three schematics passed ERC.** These historical checks do not establish compatibility with Main Board v1.1 or validate the unfinished matching Sub Board. D17 was moved clear of SW7’s courtyard, and Main Board routing and both GND fills were rebuilt. Library warnings and D12 silkscreen clipping were corrected without moving components, outlines or holes.

All manufactured-board electrical tests, actual cable/connector fit, socket/stack clearance and firmware integration remain to be performed. Review these limits before ordering. Use the supplied board version as a prototype baseline; this is not a production sign-off.

The manufacturing folders contain two-layer Gerbers (front/back copper, solder mask and silkscreen, plus Edge.Cuts) and separate plated/non-plated Excellon drill files where applicable. Routed holes/cutouts remain in Edge.Cuts; oblong strain-relief slots are included in drill data. Board thickness is recorded in each KiCad project. Confirm the manufacturer’s preview before ordering.

See the included project licenses. The models retain their source provenance; standard KiCad assets follow their library licenses.
