# ARC-164 PCBs v1.0 Prototype

**Last updated: November 7, 2026 at 12:12 PM MST (America/Denver)**

Initial three-board prototype hardware package: Main Board, Power Driver Board and LED Subboard. Includes editable KiCad sources, project-local libraries/3D models, schematic PDFs, BOMs, Gerbers, drill files, front/back previews and current cable/GPIO wiring.

All inter-board contact mappings and 19 backlight resistor/LED branches pass electrical comparison. All schematics pass ERC. All boards have zero unconnected items and no schematic parity issues. All three boards now pass DRC with zero violations. After D17 was moved clear of SW7’s courtyard, Main Board routing and both GND fills were rebuilt while preserving all saved part positions, outlines and holes.

These are untested prototypes. Complete assembled-board tests, cable/connector checks, socket/stack-height checks, and firmware integration remain outstanding. See the [GitHub prototype release](https://github.com/dgdimick/ARC-164-DCS-Display/releases/tag/pcb-v1.0-prototype).
