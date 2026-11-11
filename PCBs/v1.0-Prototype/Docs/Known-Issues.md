# Known issues — Version 1.0 prototype

**Last updated: November 10, 2026 at 5:45 PM MST (America/Denver)**

**LED Sub Board v1.2 is now published for Main Board v1.2.** I printed the latest mockup at **100%** and it passed the fit test, including **frequency and channel LED alignment and J20 connector/cable clearance**. The final layout keeps the **FREQ LEDs up 0.5 mm**, the **channel LEDs up 0.5 mm with their earlier 0.5 mm leftward adjustment**, and **J20 up 2 mm total** from the previous mounting position. The **0.75 mm gaps, 6 mm display bodies and tested 8 mm mounting stack** remain unchanged. **Use Main Board v1.2 with LED Sub Board v1.2; older Sub Boards do not match this Main Board. Assembled electrical testing is still pending.**

1. **Physical/electrical validation:** These boards have not been built and electrically validated as a complete three-board assembly. Test power polarity/current, display segment order, switches, encoders, PWM dimming and actual cable continuity.
2. **Stack height:** Display bodies extend **6 mm above the LED Sub-Board**. The Sub-Board mounts above Main at **four points**, each using a **20 mm screw, a 6 mm-thick nut and two 1 mm-thick washers**, giving **8 mm spacing**. **This Sub-Board mounting stack passed my physical test fitting on November 8, 2026**. I currently have **13.5 mm between the panel and Main Board**. I may use **14 mm** to let the LEDs sit slightly farther back from the glass. I’ll check the spacing when the manufactured PCBs arrive and add an extra spacer if needed. The Power Driver Board mounts below Main with its **components facing down**, using **10 standoffs, each longer than 20 mm**. Check the complete stack and cable clearances before assembly.
**The earlier Sub Board mockup passed my 100% print and LED alignment test behind the faceplate**, including the **0.75 mm LED gaps**, **6 mm display bodies**, and **8 mm mounting stack**. In that earlier tested adjustment, I moved the **channel LEDs 1 mm right** and the **FREQ LEDs 0.5 mm left** from the previous test layout. Each of the four mounts uses a **20 mm screw, a 6 mm-thick nut and two 1 mm washers**. **Assembled electrical testing remains to be done.** **November 10 follow-up:** The latest **Sub Board v1.2** mockup has now passed the **100% print, frequency/channel LED alignment and J20 connector/cable-clearance fit checks with Main Board v1.2**, and its files and tested STL are published. Assembled electrical testing remains pending.

3. **Cables:** Both 40-pin headers are unshrouded and can be swapped/reversed. Label and continuity-check them. Final short J10 cable and J21 cable/housing selection remain open.
4. **Firmware:** No tested ARC-164 firmware release is included. Use the supplied GPIO/cable map and verify MAX7219 configuration before functional testing.
5. **Model provenance:** The 30mm encoder representation is a sizing model adapted from a supplied shorter-shaft model; physical fit takes precedence over a 3D preview. The generic green LED model represents the specified 3mm package.

## Changes for this prototype package

- Moved only D12's reference text to clear the R6 pad; no footprint was moved.
- Saved DS1–DS6's existing close-packed courtyard geometry as the matching SC3611SURKWA_Frequency library footprint. Pad geometry, display placement and spacing did not change.
- Marked document revision metadata as 1.0 Prototype.
- Replaced obsolete two-board/32-pin/stacking/Channel-on-Subboard notes with current three-board wiring.
- Included project-local footprint/model dependencies, manufacturing files, schematic PDFs, BOMs and validation reports.

## Final Main Board reroute

After D17 was moved, all Main Board traces and both GND fills were regenerated from the new saved placement. All component positions/orientations, pad nets, outline and holes were preserved. SW1 mounting pad MH2 and SW11 GND pad 2 use solid zone connections to avoid starved thermal islands. Final Main Board DRC and connectivity checks are clean.
