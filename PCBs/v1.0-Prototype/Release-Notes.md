# ARC-164 PCBs v1.0 Prototype

**Last updated: November 9, 2026 at 3:02 PM MST (America/Denver)**

These are historical notes for the initial three-board prototype package. **The v1.0 Main Board and Sub Board downloads have been withdrawn.** [Main Board v1.1](../v1.1/Main-Board/README.md) is now available, but **it will not work with any older Sub Board**. I’m still developing the matching new Sub Board, and its files remain unpublished pending the 100% print and J20 fit test. The Power Driver Board remains at v1.0 Prototype.

At the original release, all inter-board contact mappings and 19 backlight resistor/LED branches pass electrical comparison. All schematics pass ERC. All boards have zero unconnected items and no schematic parity issues. All three boards now pass DRC with zero violations. After D17 was moved clear of SW7’s courtyard, Main Board routing and both GND fills were rebuilt while preserving all saved part positions, outlines and holes.

These are untested prototypes. Complete assembled-board tests, cable/connector checks, socket/stack-height checks, and firmware integration remain outstanding. See the [GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype).
