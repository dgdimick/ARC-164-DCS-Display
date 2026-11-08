# Additional assembly parts

**Last updated: November 8, 2026 at 1:42 AM MST (America/Denver)**

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

For **18 mm total panel-to-Main-Board spacing**, I use a **3 mm-thick nut plus a 15 mm standoff** at each mounting point. The 3 mm dimension describes the nut’s thickness; match the thread size to the mounting hardware.

For **11 mm total Main-Board-to-LED-Sub-Board spacing**, I use a **10 mm standoff plus a 1 mm-thick washer** at each mounting point.

## Power and cables

- J11 power jack: Same Sky PJ-102AH, Mouser 490-PJ-102AH.
- Suggested external supply: Mean Well GST25A05-P1J, Mouser 709-GST25A05-P1J, regulated 5V 4A. Separate IEC C13 mains cord required.
- Four Samtec TSW-120-07-L-D male 2x20 headers are used across J10/J20 on the three boards. These are included as generic header components in the schematic BOMs, not additional connectors beyond those BOM quantities.
- J20 cable: Adafruit 1988, Mouser 485-1988, approximately 6 inches/150mm, 40-pin female-female IDC.
- J10 cable: shorter 40-pin female-female, approximately 3–4 inches planned; exact supplier part pending.
- J21: three-pin 2.54mm cable/header connection; final cable/housing selection pending.
- Wired switches, panel, knobs, standoffs, cable labels and mounting hardware are separate assembly items. Final switch sourcing and mechanical stack fit require prototype checks.

See [Wiring.md](Wiring.md) for pinouts, power polarity and cable orientation.
