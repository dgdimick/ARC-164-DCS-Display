# ARC-164 LED Sub Board — Version 1.2

**Last updated: November 10, 2026 at 5:45 PM MST (America/Denver)**

**LED Sub Board v1.2 is now published for Main Board v1.2.** I printed the latest mockup at **100%** and it passed the fit test, including **frequency and channel LED alignment and J20 connector/cable clearance**. The final layout keeps the **FREQ LEDs up 0.5 mm**, the **channel LEDs up 0.5 mm with their earlier 0.5 mm leftward adjustment**, and **J20 up 2 mm total** from the previous mounting position. The **0.75 mm gaps, 6 mm display bodies and tested 8 mm mounting stack** remain unchanged. **Use Main Board v1.2 with LED Sub Board v1.2; older Sub Boards do not match this Main Board. Assembled electrical testing is still pending.**

## Downloads

- [Complete LED Sub Board v1.2 package](LED-Subboard-v1.2.zip)
- [KiCad project](Project/LED%20Subboard.kicad_pro)
- [Schematic PDF](Schematics/LED-Subboard-v1.2.pdf)
- [Component BOM](Assembly/BOM.csv)
- [Gerber and drill ZIP](LED-Subboard-v1.2-Gerbers.zip)
- [Exact fit-tested STL — print at 100%](STLs/ARC-164_LED_Subboard_v1.2_100pct.stl)
- [DRC and schematic parity report](Checks/DRC.rpt) · [ERC report](Checks/ERC.rpt)

## Displays and mounting

I use **eight QBSLDIW301GR white common-cathode digits**: six for frequency and two for channel. Each measured body is **7.6 mm wide × 13.75 mm front-face height × 6 mm deep**. With **0.75 mm gaps**, the frequency group spans **49.35 mm** and the channel pair spans **15.95 mm**.

The Sub Board mounts above **Main Board v1.2**, using four mounts, each with a **20 mm screw, 6 mm-thick nut and two 1 mm washers**, giving **8 mm spacing**. J20's cable connector clearance passed the printed mockup fit test. The footprint still represents the current vertical 40-pin header; the earlier right-angle adapter idea is not a change to this PCB footprint.

Panel-to-Main-Board spacing is currently **13.5 mm**; I may use **14 mm** after checking the manufactured PCBs. The Power Driver Board remains at **v1.0 Prototype**, below Main with its components facing down, on **10 standoffs longer than 20 mm**.

[Assembly instructions](../../v1.0-Prototype/Docs/Assembly.md) · [Wiring and J20 pinout](../../v1.0-Prototype/Docs/Wiring.md) · [Main Board v1.2](../Main-Board/README.md)

## Validation

Fresh KiCad checks report **zero DRC violations, zero unconnected items, zero schematic parity issues and zero ERC violations under the saved project settings**. The reports list checks that remain disabled. The generic display STEP is a measured-body clearance box, not a detailed manufacturer model.

The successful 100% printed fit test checks mechanical placement and connector clearance. I still need to assemble the manufactured boards and check display pinout, segment order, brightness, power and electrical operation. This is not yet an electrically validated complete radio.

## Version history

- **1.2 — November 10, 2026:** Resized Sub Board, final display placement and J20 position; latest 100% print and physical fit test passed. Published for use with Main Board v1.2.
- **1.1 — November 8, 2026:** Earlier layout, subsequently withdrawn during the J20 clearance redesign.
- **1.0 Prototype — November 7, 2026:** Initial prototype, withdrawn.

[Current PCB versions](../../README.md)
