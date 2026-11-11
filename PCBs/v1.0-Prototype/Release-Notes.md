# ARC-164 PCBs v1.0 Prototype

**Last updated: November 10, 2026 at 5:45 PM MST (America/Denver)**

**LED Sub Board v1.2 is now published for Main Board v1.2.** I printed the latest mockup at **100%** and it passed the fit test, including **frequency and channel LED alignment and J20 connector/cable clearance**. The final layout keeps the **FREQ LEDs up 0.5 mm**, the **channel LEDs up 0.5 mm with their earlier 0.5 mm leftward adjustment**, and **J20 up 2 mm total** from the previous mounting position. The **0.75 mm gaps, 6 mm display bodies and tested 8 mm mounting stack** remain unchanged. **Use Main Board v1.2 with LED Sub Board v1.2; older Sub Boards do not match this Main Board. Assembled electrical testing is still pending.**

These are historical notes for the initial three-board prototype package. **The v1.0 Main Board and Sub Board downloads have been withdrawn.** [Main Board v1.2](../v1.2/Main-Board/README.md) is now available, but **it will not work with any older Sub Board**. The matching new **Sub Board v1.2 is now published after passing the 100% mockup print and fit test**, including LED alignment and J20 clearance. The older files remain withdrawn. The Power Driver Board remains at v1.0 Prototype.

At the original release, all inter-board contact mappings and 19 backlight resistor/LED branches pass electrical comparison. All schematics pass ERC. All boards have zero unconnected items and no schematic parity issues. All three boards now pass DRC with zero violations. After D17 was moved clear of SW7’s courtyard, Main Board routing and both GND fills were rebuilt while preserving all saved part positions, outlines and holes.

These are untested prototypes. Complete assembled-board tests, cable/connector checks, socket/stack-height checks, and firmware integration remain outstanding. See the [GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype).
