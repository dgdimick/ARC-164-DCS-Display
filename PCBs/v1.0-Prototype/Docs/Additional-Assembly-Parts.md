# Additional assembly parts

**Last updated: November 8, 2026 at 12:03 PM MST (America/Denver)**

**Main Board and LED Sub Board downloads are temporarily withdrawn; please don’t order these boards yet.** I’ve resized both boards to address the **J20 cable connector clearance**, keeping the tested **LED positions, 0.75 mm gaps and 6 mm display bodies unchanged**. Both new mockups are waiting on **100% print and fit testing together with the actual J20 cable connector**. I’ll provide replacement board files after checking the fit. The earlier LED alignment and **8 mm Sub Board mounting stack** passed their tests, but clearance of the resized assembly is not yet confirmed. The new Main Board and Sub Board STLs are staying off GitHub until I’ve tested them.

The schematic BOMs list PCB components. Add the following sockets and module headers for assembly.


**I normally recommend using sockets for the DIP ICs and a removable header/socket connection for the Teensy.** This reduces the risk of overheating the ICs when soldering and makes replacement easier. Solder the empty sockets to the PCB first, let the board cool, and then insert the ICs with their pin-1 notches facing the correct way.

| Quantity | Use | Manufacturer part number | Mouser order number / link |
| ---: | --- | --- | --- |
| 2 | 24-pin DIP sockets for the MAX7219 drivers, U11 and U12; 7.62 mm row spacing, 2.54 mm pin pitch | TE Connectivity 1-2199298-8 | [571-1-2199298-8](https://www.mouser.com/ProductDetail/TE-Connectivity/1-2199298-8?qs=fK8dlpkaUMsSY7Gqcrol0Q%3D%3D) |
| 1 | 14-pin DIP socket for the 74AHCT125 buffer, U13; 7.62 mm row spacing, 2.54 mm pin pitch | TE Connectivity 1-2199298-3 | [571-1-2199298-3](https://www.mouser.com/en/ProductDetail/TE-Connectivity/1-2199298-3?qs=fK8dlpkaUMtBOtVI99wRlQ%3D%3D) |
| 2 | Single-row 24-pin male headers for the Teensy 4.1's two outer rows; 2.54 mm pitch | Samtec TSW-124-07-T-S | [200-TSW12407TS](https://www.mouser.com/en/ProductDetail/Samtec/TSW-124-07-T-S?qs=rU5fayqh%252BE26VY6qw728rQ%3D%3D) |
| 2 | Matching single-row 24-pin female sockets on the Power Driver Board; 2.54 mm pitch | Samtec SSW-124-01-T-S | [200-SSW12401TS](https://www.mouser.com/ProductDetail/Samtec/SSW-124-01-T-S?qs=iT52DjcXudvCUishYlzKnw%3D%3D) |

All of these parts are through-hole and can be hand soldered. The Teensy still needs its male headers soldered on unless you buy it with pins already fitted; use a temperature-controlled iron and avoid prolonged heating. The female sockets let you unplug the complete Teensy module from the Power Driver Board. Check the added socket/header height when setting the clearance to the board above it. Check current supplier pricing.


## Panel mounting hardware

**The LED positions on the v1.1 mockup passed my 100% print and physical alignment test behind the faceplate**, including the **0.75 mm LED gaps**, **6 mm display bodies**, and **8 mm mounting stack**. In the final adjustment, I moved the **channel LEDs 1 mm right** and the **FREQ LEDs 0.5 mm left** from the previous test layout. Each of the four mounts uses a **20 mm screw, a 6 mm-thick nut and two 1 mm washers**. **Assembled electrical testing remains to be done.**

I currently have **13.5 mm between the panel and Main Board**. I may use **14 mm** to let the LEDs sit slightly farther back from the glass. I’ll check the spacing when the manufactured PCBs arrive and add an extra spacer if needed. The final spacer and mounting-hardware combination is still to be confirmed.

The **LED Sub-Board mounts above the Main Board**, with its bottom facing the Main Board’s top. I use **four Sub-Board mounts**, each with a **20 mm screw, a 6 mm-thick nut, and two 1 mm-thick washers**, giving **8 mm spacing** between the Main Board and LED Sub-Board.

| Quantity | Mounting hardware | Requirement |
| ---: | --- | --- |
| **4** | 20 mm screws for the LED Sub-Board mounts | One per mount; match the thread size to the nuts. |
| **4** | 6 mm-thick nuts for the LED Sub-Board mounts | One per mount; 6 mm is the thickness, not the thread diameter. |
| **8** | 1 mm-thick washers for the LED Sub-Board mounts | Two per mount; nut plus washers gives **8 mm spacing**. |
| **10** | Standoffs connecting the Power Driver Board below the Main Board, components facing down | **Each longer than 20 mm**; choose the exact length to clear components, sockets, Teensy headers, and cables. Match the thread size to the mounting hardware. |

## Power and cables

- J11 power jack: Same Sky PJ-102AH, Mouser 490-PJ-102AH.
- Suggested external supply: Mean Well GST25A05-P1J, Mouser 709-GST25A05-P1J, regulated 5V 4A. Separate IEC C13 mains cord required.
- Four Samtec TSW-120-07-L-D male 2x20 headers are used across J10/J20 on the three boards. These are included as generic header components in the schematic BOMs, not additional connectors beyond those BOM quantities.
- J20 cable: Adafruit 1988, Mouser 485-1988, approximately 6 inches/150mm, 40-pin female-female IDC.
- J10 cable: shorter 40-pin female-female, approximately 3–4 inches planned; exact supplier part pending.
- J21: three-pin 2.54mm cable/header connection; final cable/housing selection pending.
- Wired switches, panel, knobs, standoffs, cable labels and mounting hardware are separate assembly items. Final switch sourcing and mechanical stack fit require prototype checks.

See [Wiring.md](Wiring.md) for pinouts, power polarity and cable orientation.
