# ARC-164 LED Sub Board — Version 1.1

**Last updated: November 8, 2026 at 10:44 AM MST (America/Denver)**

**PCB ordering is on hold: the J20 cable connector does not clear the Main Board.** I need to redesign **both the Main Board and LED Sub Board** to provide enough connector and cable clearance before ordering. I’ll **keep the tested LED positions, 0.75 mm gaps and 6 mm display-body height unchanged** while revising the connector area. The LED alignment and 8 mm mounting-stack fit passed, but the complete assembly does not yet clear the cable connector. I still need to test-fit the revised boards with the actual connector and cable before ordering; assembled electrical testing also remains pending.

**The LED positions on the v1.1 mockup passed my 100% print and physical alignment test behind the faceplate**, including the **0.75 mm LED gaps**, **6 mm display bodies**, and **8 mm mounting stack**. In the final adjustment, I moved the **channel LEDs 1 mm right** and the **FREQ LEDs 0.5 mm left** from the previous test layout. Each of the four mounts uses a **20 mm screw, a 6 mm-thick nut and two 1 mm washers**. **Assembled electrical testing remains to be done.**

## Reference downloads — do not order these boards yet

- [Complete v1.1 package](LED-Subboard-v1.1.zip)
- [KiCad project](Project/LED%20Subboard.kicad_pro)
- [Schematic PDF](Schematics/LED-Subboard-v1.1.pdf)
- [Component BOM](Assembly/BOM.csv)
- [Gerber and drill ZIP](LED-Subboard-v1.1-Gerbers.zip)
- [Tested STL mockup — print at 100%](STLs/ARC-164_LED_Subboard_v1.1_100pct.stl)
- [Board checks](Checks/DRC.rpt) and [schematic checks](Checks/ERC.rpt)
- [Assembly instructions](../../v1.0-Prototype/Docs/Assembly.md) and [J20 wiring](../../v1.0-Prototype/Docs/Wiring.md)

The board carries eight **QBSLDIW301GR white common-cathode digits**: six frequency digits spanning **49.35 mm** and two channel digits spanning **15.95 mm**, with **0.75 mm gaps**. Each display body measures **7.6 mm wide × 13.75 mm high × 6 mm deep**. I kept the J20 connector's distance from the board edge and centered it horizontally between the upper mounting holes.

The Sub Board mounts above the Main Board. I currently have **13.5 mm between the panel and Main Board**. I may use **14 mm** to let the LEDs sit slightly farther back from the glass. I’ll check the spacing when the manufactured PCBs arrive and add an extra spacer if needed. The Power Driver Board mounts below the Main Board, components facing down, on **10 standoffs longer than 20 mm**.

Fresh KiCad checks report **zero DRC violations, zero unconnected items, zero schematic parity issues, and zero ERC violations under the saved project settings**. The reports list checks that remain disabled. Physical mockup fitting does not replace assembly and electrical testing. The bundled display STEP model is a simple measured-body clearance box.

The Main Board and Power Driver Board remain at **v1.0 Prototype**. Their existing J20 cable pinout is unchanged. The older complete three-board ZIP contains the old LED board; this v1.1 download records the current LED layout, but **it also requires the J20 clearance redesign before ordering**.

## Version history

- **1.1 — November 8, 2026:** White-display layout, 0.75 mm gaps, final FREQ/channel placement and centered J20 connector. I printed the mockup at 100% and passed physical fit testing. Electrical testing remains pending.
- [1.0 Prototype — November 7, 2026](../../v1.0-Prototype/LED-Subboard/README.md): Initial prototype, retained for reference.

[Current PCB overview](../../README.md)
