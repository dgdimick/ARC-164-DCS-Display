# Known issues — Version 1.0 prototype

**Last updated: November 9, 2026 at 2:59 PM MST (America/Denver)**

**Main Board v1.1 is published, but it will not work with any currently or previously published LED Sub Board.** I’ve resized the Main Board and am still working on its matching redesigned Sub Board. **The new Sub Board files and test STL remain unpublished until I finish the 100% print and fit test, including the J20 cable connector.** I’m keeping the tested LED positions and 0.75 mm gaps. Please wait for the matching Sub Board and confirmed assembly clearance before ordering a compatible set. Assembled electrical testing remains pending.

1. **Physical/electrical validation:** These boards have not been built and electrically validated as a complete three-board assembly. Test power polarity/current, display segment order, switches, encoders, PWM dimming and actual cable continuity.
2. **Stack height:** Display bodies extend **6 mm above the LED Sub-Board**. The Sub-Board mounts above Main at **four points**, each using a **20 mm screw, a 6 mm-thick nut and two 1 mm-thick washers**, giving **8 mm spacing**. **This Sub-Board mounting stack passed my physical test fitting on November 8, 2026**. I currently have **13.5 mm between the panel and Main Board**. I may use **14 mm** to let the LEDs sit slightly farther back from the glass. I’ll check the spacing when the manufactured PCBs arrive and add an extra spacer if needed. The Power Driver Board mounts below Main with its **components facing down**, using **10 standoffs, each longer than 20 mm**. Check the complete stack and cable clearances before assembly.
**The LED positions on the v1.1 mockup passed my 100% print and physical alignment test behind the faceplate**, including the **0.75 mm LED gaps**, **6 mm display bodies**, and **8 mm mounting stack**. In the final adjustment, I moved the **channel LEDs 1 mm right** and the **FREQ LEDs 0.5 mm left** from the previous test layout. Each of the four mounts uses a **20 mm screw, a 6 mm-thick nut and two 1 mm washers**. **Assembled electrical testing remains to be done.**

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
