# Known issues — Version 1.0 prototype

**Last updated: November 7, 2026 at 12:12 PM MST (America/Denver)**

1. **Physical/electrical validation:** These boards have not been built and electrically validated as a complete three-board assembly. Test power polarity/current, display segment order, switches, encoders, PWM dimming and actual cable continuity.
2. **Stack height:** Main-to-LED standoffs 7mm; faceplate-to-Main standoffs 15mm. Power Driver spacing below Main remains to be finalized, especially with DIP sockets and removable Teensy headers. The Teensy 3D view does not include the additional connector stack height.
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
