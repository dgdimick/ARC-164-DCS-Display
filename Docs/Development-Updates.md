# ARC-164 development updates

**Last updated: November 10, 2026 at 7:22 PM MST (America/Denver)**

[Read the latest development update](../README.md#development-update--november-10-2026) in the main README.

## Development update — November 9, 2026

I’ve published [Main Board v1.2](../PCBs/v1.2/Main-Board/README.md) with **J10 at my chosen position, SW12 and SW13 aligned below R4, and updated routing and ground fills**. The PCB/schematic revision fields, fabrication downloads and print mockup are updated too. At that stage, Main Board v1.2 did not match any published Sub Board. **November 10 follow-up: Sub Board v1.2 has now passed the mockup fit test and is published.**

## Development update — November 8, 2026

**The earlier Sub Board mockup passed my 100% print and LED alignment test behind the faceplate**, including the **0.75 mm LED gaps**, **6 mm display bodies**, and **8 mm mounting stack**. In that earlier tested adjustment, I moved the **channel LEDs 1 mm right** and the **FREQ LEDs 0.5 mm left** from the previous test layout. Each of the four mounts uses a **20 mm screw, a 6 mm-thick nut and two 1 mm washers**. **Assembled electrical testing remains to be done.** [Current LED Sub Board v1.2](../PCBs/v1.2/LED-Subboard/README.md). This November 8 update describes the earlier layout. **The current matched pair is Main Board v1.2 and Sub Board v1.2, both published; the Power Driver Board remains at v1.0 Prototype.** **November 10 follow-up:** The latest **Sub Board v1.2** mockup has now passed the **100% print, frequency/channel LED alignment and J20 connector/cable-clearance fit checks with Main Board v1.2**, and its files and tested STL are published. Assembled electrical testing remains pending.

## Development update — November 7, 2026

I initially published Version 1.0 prototypes of all three boards. The matched **Main Board v1.2 and LED Sub Board v1.2** are published; see the [PCB download overview](../PCBs/README.md) for individual board files and fabrication ZIPs. The Power Driver Board remains available, along with the [three-board wiring notes](../PCBs/v1.0-Prototype/Docs/Wiring.md). The Sub Board v1.2 mockup has passed the **100% print, LED alignment and J20 connector/cable-clearance checks**. **Main Board v1.2 matches the published Sub Board v1.2, which passed the 100% printed fit test. Older Sub Board v1.0/v1.1 layouts do not match it; assembled electrical testing remains pending.**

I’ve checked the designs in KiCad, and **all three boards pass the design-rule and schematic electrical checks**, with no unconnected items or differences between the schematics and PCBs. The cable pinouts and all 19 backlight LED/resistor connections have been checked too.

**I haven’t assembled and electrically tested these boards yet, so please treat them as prototypes.** I still need to check the complete stack, sockets, cables, and firmware together. I’ll share pictures and what I find as I work through my build. If you give them a try, I’d love to see your build and hear how it goes in [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions).

I’ve replaced the two-pin power-input header with a **PCB-mounted PJ-102AH barrel power jack at J11 on the Power Driver Board**. The jack sits at the right-hand board edge with its opening facing outward for easy access. It accepts **regulated 5 V DC through a 5.5 × 2.1 mm center-positive plug**.

My recommended supply is the **MEAN WELL GST25A05-P1J (5 V, 4 A)**. You’re welcome to use another supply; just make sure it provides **well-regulated 5 V DC**, enough current, and the correct plug and polarity. See the [power-supply parts-list section](../README.md#external-regulated-5-v-power-supply) for the Mouser link, specifications, and mains-cord requirement. The board does not convert a higher input voltage to 5 V.

I’ve also added [recommended IC sockets and Teensy headers](../README.md#recommended-ic-sockets-and-teensy-headers) to the parts list, with Mouser links: **two 24-pin sockets for U11/U12, one 14-pin socket for U13, and two pairs of 24-pin male headers and female sockets for the Teensy**. I normally recommend these to reduce the risk of overheating the ICs during soldering and to make replacement easier. Solder the empty IC sockets first, let the board cool, and then install the chips. The Teensy’s male headers still need soldering unless its pins are already fitted.

## Development update — November 6, 2026

**PC Flights confirmed they can make the modified ARC-164 panel for US$57 plus a US$20 custom-order fee—US$77 total before any shipping or other charges.** This is their quote for the requested panel changes; I haven’t placed the custom order yet.

**November 9 follow-up:** [PC Flights](https://pcflights.com/) has replied to my request about making the ARC-164 panel with larger holes available to other builders. **They’ll make it on request, but don’t plan to list it on their website for now**, since I’m the first person to ask for these changes. If you want this version, **contact PC Flights and ask for the modified ARC-164 panel with larger holes instead of the default panel**.

I’ll continue building the rotary-encoder version of the ARC-164. The rotary-switch version can wait while I finish the ARC-164 PCBs and return to ARC-210 testing. **I’ll wait to buy the modified panel until I’m ready to work on ARC-164 Version 2. That’s still off in the future, with no release date planned.**

## Development update — November 4, 2026

I’ve sent **PC Flights a request for a complete new ARC-164 panel** with the five FREQ shaft holes enlarged in **both the front faceplate and clear backing panel**, keeping their centers unchanged. I asked for the holes to match the existing MAIN/PRESET diameter—approximately **10.2 mm in the supplied drawing**—and noted that the Channel control already has a larger hole and that PC Flights uses a similar larger-hole arrangement on its ARC-210 panel.

I also requested **anti-rotation slots in the clear backing panel** and supplied a marked drawing and proposed DXF for review. The slot dimensions, orientation, and any matching relief needed in the front faceplate still need confirmation. I understand this would require purchasing a **complete new panel**.

This would let me revisit frequency rotary switches using the [earlier staggered mounting concept](https://github.com/dgdimick/ARC-164-DCS-Display/blob/394ed3a46d2bc5caa23bab62e20b150761d81306/images/ARC-164_Staggered_PCB_Mount_Concept.png): **two PCBs total for the frequency controls, one carrying the two-switch group and the other carrying the three-switch group**. The picture is historical; its shaft-length labels are not final production dimensions.

**November 6 follow-up:** PC Flights confirmed they could make the requested changes and supplied the quote in the November 6 update. **Their November 9 reply confirms availability on request, without a website listing for now.** Final dimensions and mechanical fit still need checking. The current frequency-encoder design remains my working baseline.

**The rotary-switch alternative is deferred. My priority is to finish the current ARC-164 PCBs, then take a break from design work and return to ARC-210 testing.** I’ll revisit the modified panel, switch selection, and parts list when I return to the rotary-switch version.
