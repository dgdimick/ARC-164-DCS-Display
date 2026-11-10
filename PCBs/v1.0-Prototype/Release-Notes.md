# ARC-164 PCBs v1.0 Prototype

**Last updated: November 9, 2026 at 6:23 PM MST (America/Denver)**

The latest Sub Board mockup moves both channel LEDs **up 0.5 mm** and J20 **up 2 mm total across the last two moves**. The earlier **0.5 mm leftward channel adjustment** is retained; the frequency LED positions, **0.75 mm gaps and 6 mm display bodies** are unchanged. **The 100% print, channel LED alignment and J20 connector/cable-clearance checks with Main Board v1.2 are still pending before I publish the new Sub Board files or STL.**

These are historical notes for the initial three-board prototype package. **The v1.0 Main Board and Sub Board downloads have been withdrawn.** [Main Board v1.2](../v1.2/Main-Board/README.md) is now available, but **it will not work with any older Sub Board**. I’m still developing the matching new Sub Board, and its files remain unpublished pending the 100% print and J20 fit test. The Power Driver Board remains at v1.0 Prototype.

At the original release, all inter-board contact mappings and 19 backlight resistor/LED branches pass electrical comparison. All schematics pass ERC. All boards have zero unconnected items and no schematic parity issues. All three boards now pass DRC with zero violations. After D17 was moved clear of SW7’s courtyard, Main Board routing and both GND fills were rebuilt while preserving all saved part positions, outlines and holes.

These are untested prototypes. Complete assembled-board tests, cable/connector checks, socket/stack-height checks, and firmware integration remain outstanding. See the [GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype).
