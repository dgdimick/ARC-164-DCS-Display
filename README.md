# ARC-164 Radio Panel for DCS

**Last updated: November 7, 2026 at 11:06 AM MST (America/Denver)**
<!-- Refresh this timestamp whenever this README changes; use the actual current America/Denver date and time with the correct MST/MDT abbreviation. -->

<p align="center">
  <img src="images/ARC-164_uhf_panel.jpg" width="500" alt="ARC-164 UHF radio panel reference photo">
</p>

*Panel reference photo: PC Flights.*

I’m developing the hardware and firmware for my ARC-164 radio panel.

## Development update — November 7, 2026

The **Power Driver Board now has a PCB-mounted PJ-102AH barrel power jack at J11**, replacing the two-pin power-input header. The jack sits at the right-hand board edge with its opening facing outward for easy access. It accepts **regulated 5 V DC through a 5.5 × 2.1 mm center-positive plug**.

The recommended supply is the **MEAN WELL GST25A05-P1J (5 V, 4 A)**. Other supplies are welcome, but they must provide **well-regulated 5 V DC**, sufficient current, and the correct plug and polarity. See the [power-supply parts-list section](#external-regulated-5-v-power-supply) for the Mouser link, specifications, and mains-cord requirement. The board does not convert a higher input voltage to 5 V.

## Physical mockup — November 6, 2026

[![ARC-164 physical mockup showing the faceplate, control shafts, display covers, and printed board assembly](images/ARC-164_Mockup.jpg)](images/ARC-164_Mockup.jpg)

Here’s my current ARC-164 mockup, showing the faceplate, control shafts, and display covers together with the 3D-printed board assembly. I’m using this to check the mechanical layout and clearances as I continue building the encoder version. This is a physical mockup, not a completed or electrically tested panel. Click the photo to see it full size.

## Development update — November 6, 2026

**PC Flights confirmed they can make the modified ARC-164 panel for US$57 plus a US$20 custom-order fee—US$77 total before any shipping or other charges.** This is their quote for the requested panel changes; I haven’t placed the custom order yet.

I’ve asked whether they would make the modified panel a **stocked option for other builders**, so people following this project could buy it without arranging a special order. I’d be happy to buy one and build with it. **A stocked option has not been confirmed; I’m waiting for their reply.** **While I wait for their reply, I’ll continue building the rotary-encoder version of the ARC-164. I’ll revisit the rotary-switch version later, after completing the ARC-186 and ARC-210 v2.0 projects.**

## Development update — November 4, 2026

I’ve sent **PC Flights a request for a complete new ARC-164 panel** with the five FREQ shaft holes enlarged in **both the front faceplate and clear backing panel**, keeping their centers unchanged. I asked for the holes to match the existing MAIN/PRESET diameter—approximately **10.2 mm in the supplied drawing**—and noted that the Channel control already has a larger hole and that PC Flights uses a similar larger-hole arrangement on its ARC-210 panel.

I also requested **anti-rotation slots in the clear backing panel** and supplied a marked drawing and proposed DXF for review. The slot dimensions, orientation, and any matching relief needed in the front faceplate still need confirmation. I understand this would require purchasing a **complete new panel**.

This would let me revisit frequency rotary switches using the [earlier staggered mounting concept](https://github.com/dgdimick/ARC-164-DCS-Display/blob/394ed3a46d2bc5caa23bab62e20b150761d81306/images/ARC-164_Staggered_PCB_Mount_Concept.png): **two PCBs total for the frequency controls, one carrying the two-switch group and the other carrying the three-switch group**. The picture is historical; its shaft-length labels are not final production dimensions.

**November 6 follow-up:** PC Flights has confirmed they can make the requested changes and supplied the quote above. Stocked availability, final dimensions, and mechanical fit still need confirmation. The current frequency-encoder design remains the working baseline while I investigate this option.

**The rotary-switch alternative is deferred until after the ARC-186 and ARC-210 v2.0 projects. I’ll continue building the frequency-encoder version now, including its LED display.** I’ll revisit the modified panel, switch selection, and parts list when I return to the rotary-switch version.

## Current development order

For these two radio panels, I plan to build and test the **ARC-164**, followed by the **ARC-186**, then investigate additional aircraft support with matching physical radio panels.

**This order may change based on user feedback and interest.** These are plans, not fixed release dates.

## Other SIMPIT panels

Once I’ve finished the radio panels, I plan to build other panels for my SIMPIT, including the **SAS and emergency trim panels**. I’ll share those projects as they develop. These are future plans.

## Through-hole components

While I could use surface-mount (SMD) parts to make the boards smaller, I plan to use through-hole components to make the project easier for everyone to build and solder with basic tools.

I chose the listed component suppliers because I’m aiming for better-quality parts than I generally expect from generic Amazon listings, even if they cost a little more. Parts from Amazon may work, and I use some myself, but substitutes may have different dimensions or pin spacing and may not fit the PCBs I designed for this project. Please compare the exact part specifications and PCB footprint before buying a substitute.

## Recorded component costs

These are my recorded purchases so far, in **US dollars**. The total includes rotary switches bought before I returned to frequency encoders; it is not a shopping list for the current design. The **A11015RNCQ switches are 10-position switches** and were the wrong parts for the ARC-164. **DigiKey did not cancel my order, so I’ll keep the A11015RNCQ switches as parts for ARC-210 V2**.

| Item | Quantity | Cost (USD) |
|---|---:|---:|
| QBSLDIW301GR white seven-segment LED digits — earlier purchase; superseded by SC36-11SURKWA in the current build plan | 10 | $17.43 |
| A12515RNCQ rotary switches — earlier long-shaft selection; no longer the current MAIN/PRESET choice | 5 | $55.66 |
| A11015RNCQ rotary switches — 10 positions; DigiKey order not canceled, retained for ARC-210 V2 | 3 | $35.07 |
| Tax and tariffs on the rotary-switch and LED order | — | $27.13 |
| Toggle-switch purchase | — | $13.51 |
| Toggle-switch purchase | — | $10.76 |
| Faceplate | 1 | $57.00 |
| Faceplate shipping | — | $13.59 |
| Pushbutton switches | — | $7.99 |
| Teensy 4.1 | 1 | $29.60 |
| Teensy shipping | — | $8.35 |
| **Running total** | | **$276.09** |

My Teensy 4.1 cost **$37.95 including shipping**, and my faceplate cost **$70.59 including shipping**. The rotary switches and LEDs came to **$108.16**, or **$135.29 including tax and tariffs**. Those charges are already included in the running total. I bought two spare LED digits and one spare A12515RNCQ switch because the quantity price breaks saved me money compared with buying only the quantities I originally planned to use. I still need to verify the selected toggle switches’ fit and operation.

**The VOL encoder isn’t included in the total yet.** My current selection for VOL, FREQ, and channel is **PEC11R-4230F-S0024 with a 30 mm shaft**, sourced from Mouser. I’ll add actual encoder costs to this purchase history once the order is confirmed.

**This total is before PCBs, display drivers, resistors, connectors, and the other remaining parts. It is not the complete build cost.** I’ll update the total as I buy the remaining parts. Additional shipping or fees not listed above are also excluded.

## Order sheet — rotary controls and LED digits

**Current build: rotary encoders.** I’ll continue building the encoder version while waiting for PC Flights’ reply about a stocked modified panel. The rotary-switch alternative is deferred until after the ARC-186 and ARC-210 v2.0 projects. The order sheet below is for the encoder version; quantities and fit still need final checks before purchasing.

This is my order sheet for **one ARC-164 panel**, updated **November 4, 2026**. I’ll buy the **30 mm encoders and SC36-11SURKWA LED digits from Mouser**. The MAIN and PRESET switches remain on the DigiKey list. These are full build quantities; I’ll deduct parts I already have before ordering.

| Quantity | Use | Manufacturer part number | Supplier / order number | Estimated unit price (USD) | Estimated total (USD) |
| ---: | --- | --- | --- | ---: | ---: |
| 7 | Five FREQ encoders, channel encoder, and VOL | PEC11R-4230F-S0024 | [Mouser: 652-PEC11R-4230F-S24](https://www.mouser.com/en/ProductDetail/Bourns/PEC11R-4230F-S0024?qs=Zq5ylnUbLm6MC5h%2FLr6Brg%3D%3D) | $2.07 | $14.49 |
| 2 | MAIN and PRESET rotary switches | A12505RNCQ | [DigiKey: CKN10203-ND](https://www.digikey.com/en/products/detail/c-k/A12505RNCQ/2043159) | $13.41 | $26.82 |
| 10 | Red 0.36-inch common-cathode seven-segment LED digits | SC36-11SURKWA | [Mouser: 604-SC36-11SURKWA](https://www.mouser.com/en/ProductDetail/Kingbright/SC36-11SURKWA?qs=FRBiz4Wv1YMkVf5BvlPtDA%3D%3D) | $1.45 | $14.50 |
| | **Estimated subtotal** | | | | **$55.81** |

All seven encoders have **30 mm shafts**. MAIN and PRESET use the **same A12505RNCQ switch**, with the stop ring set to **4 positions for MAIN** and **3 positions for PRESET**; both index at **45° per position**.

Prices use the quantity-five encoder tier, quantity-one switch tier, and Mouser’s quantity-ten SC36-11SURKWA LED tier. The LED price is $1.45 each ($14.50 for ten), checked November 4, 2026. Prices can change; shipping, tax, and tariffs are excluded. This estimate is separate from my recorded purchases.

**This is not the complete build BOM.** TONE, SQL, STATUS, display drivers, other display components, resistors, capacitors, connectors, PCBs, and other remaining parts are excluded.

### External regulated 5 V power supply

| Quantity | Use | Manufacturer part number | Supplier / order number |
| ---: | --- | --- | --- |
| 1 | Regulated 5 V, 4 A supply for the displays and panel backlighting | MEAN WELL GST25A05-P1J | [Mouser: 709-GST25A05-P1J](https://www.mouser.com/en/ProductDetail/MEAN-WELL/GST25A05-P1J?mgh=1&qs=drgMNd%252BkGPOX8brSXUPVtQ%3D%3D) |

**You can use another power supply, but it must provide well-regulated 5 V DC**, with a voltage tolerance of **±5% or better**, enough current for the connected panels, and a **5.5 mm outer / 2.1 mm inner, center-positive barrel plug** to fit J11. The recommended supply provides 4 A; the circuit draws only the current it needs. The Power Driver Board does not reduce a higher input voltage to 5 V.

The GST25A05-P1J requires a separate **IEC C13 mains cord** (the standard desktop-computer type). See the [MEAN WELL datasheet](https://www.meanwell.com/Upload/PDF/GST25A/GST25A-SPEC.PDF). The Teensy remains powered through USB; the external supply powers the display and backlight circuits. The supply and mains cord are **not included in the rotary-control and LED subtotal above**; check current supplier pricing.

### USB adapter cable

Use **one USB-C-to-Micro-B data cable per panel** to connect the Teensy 4.1’s Micro-B device port to a computer or hub with a USB-C port. The linked option is a **1 ft (30.5 cm), male-to-male cable carrying both data and power**:

[Amazon — USB-C-to-Micro-B adapter cable](https://www.amazon.com/dp/B0BD36TZBK)

This replaces the standard USB Micro-B data cable when using a USB-C port; you only need one suitable USB data cable per panel. A charge-only cable will not carry DCS-BIOS communications or program the Teensy. Choose a length that suits your installation and check the current supplier price.

The USB cable is separate from the rotary-control and LED subtotal above; its cost has not been added to the recorded purchase history.

### Additional Mouser items — green panel backlighting

I’ve selected **Kingbright WP710A10SGD**, a **3 mm through-hole green LED with a diffused lens**, for the ARC-164 and ARC-210 panel-backlighting plan. See [Mouser part 604-WP710A10SGD](https://www.mouser.com/ProductDetail/Kingbright/WP710A10SGD?qs=jBF9H7RTBaS5vBvRdVQZww%3D%3D) and the [Kingbright datasheet](https://www.kingbrightusa.com/images/catalog/spec/wp710a10sgd.pdf). Final brightness, light spread, and mounting fit behind the lettering still need testing.

**Backlight LED quantities are still being decided.** The figures below are provisional planning estimates, not finalized purchase quantities. I’ll confirm them after laying out the LEDs behind the lettering and testing light coverage.

| Provisional quantity | Allocation | Manufacturer part number | Mouser order number |
| ---: | --- | --- | --- |
| 24 | ARC-164 backlighting — initial estimate of 20–24 LEDs | WP710A10SGD | 604-WP710A10SGD |
| 38 | ARC-210 backlighting | WP710A10SGD | 604-WP710A10SGD |
| **62 total** | **Planning total only; final quantity TBD, excluding spares** | **WP710A10SGD** | **604-WP710A10SGD** |

These LEDs require **one current-limiting resistor per LED branch** on the regulated 5 V supply. I’ll start brightness testing with **330 Ω resistors**, approximately **8.5 mA per LED** at the datasheet’s typical 2.2 V forward voltage; actual current and brightness will vary. For the provisional 62-LED estimate, that nominal current would draw approximately 0.53 A at full duty, excluding the displays and controllers. The final resistor selection and power budget remain subject to testing.

The LEDs will sit behind the lettering, with opaque shielding around display windows. They will use the panel-backlighting driver, not the MAX7219 segment outputs. **Confirm price and availability in the Mouser cart; these additional LEDs and their resistors are not included in the $55.81 ARC-164 subtotal above.**

### Additional item for my Mouser order — emergency trim panel

I’ll add this part to the same Mouser order as the ARC-164 encoders. It is for my **A-10 emergency pitch/roll trim panel**, not the ARC-164 radio.

| Quantity | Use | Manufacturer part number | Mouser order number | Estimated cost (USD) |
| ---: | --- | --- | --- | --- |
| 1 | Emergency pitch/roll trim directional switch | Alps Alpine RKJXT1F42001 | [688-RKJXT1F42001](https://www.mouser.com/en/ProductDetail/Alps-Alpine/RKJXT1F42001?qs=6EGMNY9ZYDTsBzSTrhiL0w%3D%3D) | Confirm USD price in cart |

This is a **four-direction switch with a center pushbutton and rotary encoder**. I plan to use its four directions for emergency pitch and roll trim; the center pushbutton and rotary encoder will remain unused. Physical mounting, knob fit, and operating feel still need checking. Its cost is **not included in the $55.81 ARC-164 subtotal** above.

## Things that need to be completed

**Last updated: November 4, 2026 at 8:37 AM MST (America/Denver)**
<!-- Refresh this section timestamp whenever the work list changes, using the actual America/Denver time and MST/MDT. -->

This is my current work list for the hardware, firmware, testing, and build instructions.

1. **Panel layout and parts:** Confirm dimensions, mounting clearances, controls, and the complete parts list. **TONE and SQL switches:** Select the exact parts and verify their mounting dimensions, required operation and travel, and clearances before finalizing the PCB. Test-fit **six SC36-11SURKWA digits for frequency and two for preset**, using [Mouser part 604-SC36-11SURKWA](https://www.mouser.com/en/ProductDetail/Kingbright/SC36-11SURKWA?qs=FRBiz4Wv1YMkVf5BvlPtDA%3D%3D). Check digit visibility and brightness through the smoked covers, pinout, mounting height, spacing, and clearance within the 53.5 × 17.5 mm frequency window and 22 × 17.5 mm preset window.
2. **PCB, schematic, and rotary-encoder design:** Continue the current five-frequency-encoder design, with no frequency-switch resistor ladders, while following up with PC Flights about stocking the modified panel. Revisit the alternative staggered rotary-switch arrangement after completing the ARC-186 and ARC-210 v2.0 projects. Design the Main PCB with the MAIN and PRESET rotary switches, their resistor ladders, controller, and display circuitry. Update the rotary-encoder schematic, PCB footprints, and 3D models for the **PEC11R-4230F-S0024 encoders with 30 mm shafts**, including the FREQ, channel, and VOL controls. Place and connect VOL, reroute the encoder PCB, and check its connections to the Main PCB. Design the small display PCB and its standoff mounting, with the display soldered directly to the board; set the height after checking it against the faceplate. Finalize Teensy pin assignments, check the complete electrical design, and verify clearances and test fitting before ordering boards.
3. **Printed parts:** Design and test-fit the required knobs, brackets, and spacers with the selected hardware. Verify shaft engagement, knob retention, mounting height, and clearance behind the faceplate.
4. **DCS-BIOS mappings and any needed changes:** Check which inputs and display outputs are already available for this radio. Identify missing data, make any necessary export changes, and document them. Check the correct ARC-164 radio instance for each intended A-10 variant.
5. **Firmware:** Write the control and display firmware and verify USB communication with DCS-BIOS. Implement DCS-BIOS-controlled MAX7219 display brightness and PWM panel backlighting, with separate brightness curves and off-state handling; see the [lighting design plan](#dcs-bios-display-brightness-and-panel-backlighting).
6. **Bench and board testing:** Test the controls, displays, and power requirements together, then assemble and electrically test the manufactured boards.
7. **Dual ARC-164 support:** Integrate support for aircraft with two ARC-164 radios, such as the A-10C. I plan to use a single jumper on the Main PCB to select whether each panel operates as **Radio 1 or Radio 2**. Design the jumper input and firmware selection, verify the DCS-BIOS mappings for both radio instances, and test both panels together.
8. **Testing in DCS:** Check control operation, display updates, startup behavior, reconnection, and extended reliability with the intended aircraft and the other radio panels connected.
9. **Documentation:** Publish assembly instructions, wiring diagrams, final parts and print quantities, PCB ordering files, firmware loading steps, DCS-BIOS setup requirements, and troubleshooting notes.
10. **Assembly pictures:** During assembly, take clear pictures of component placement, soldering, wiring, and mounting, including both sides of each PCB with the silkscreen markings visible. Add the pictures to the assembly instructions so other builders can follow along.


## Controller choice — Teensy 4.1

I’m using the **Teensy 4.1** for its compact size and room for the panel’s controls and displays. It runs at **600 MHz**, compared with **16 MHz for the classic Arduino Uno R3, Mega 2560, and ATmega328P Nano**. I still need to finalize the pin assignments. See the [Teensy specifications](https://www.pjrc.com/store/teensy41.html).

I’ll use USB for DCS-BIOS; Ethernet isn’t needed. The Teensy uses **3.3 V logic**, and its inputs are **not 5 V tolerant**, so I’ll design the display-driver connections accordingly.

## Seven-segment display plan

I’ve selected **Kingbright SC36-11SURKWA** red, common-cathode, single-digit seven-segment displays for both frequency and preset. I’ll order **10 from [Mouser, part 604-SC36-11SURKWA](https://www.mouser.com/en/ProductDetail/Kingbright/SC36-11SURKWA?qs=FRBiz4Wv1YMkVf5BvlPtDA%3D%3D)**: **six for frequency, two for preset, and two spares**. These replace the earlier PC Flights amber display plan and the QBSLDIW301GR selection; the earlier purchases remain in the cost history.

Each display has a **7.5 × 14 × 8.5 mm body**, **9.14 mm (0.36-inch) digits**, and a right-hand decimal point. Common cathodes are on **pins 1 and 6**. I’ll use the SC36-11SURKWA footprint and pinout when designing the display boards. See the [Kingbright datasheet](https://www.kingbrightusa.com/images/catalog/SPEC/SC36-11SURKWA.pdf).

### Frequency display

I’ll use **six SC36-11SURKWA digits** to show a frequency such as **251.000**. Six bodies side by side occupy **45 × 14 mm before spacing**, within the **53.5 × 17.5 mm frequency window**. Final spacing, alignment, brightness through the smoked cover, and clearance behind the faceplate still need physical testing.

### Display mounting

I’ll solder the digits directly to display PCBs mounted on standoffs. I’ll set the standoff height during test fitting so the digits sit at the correct height behind the windows, with clearance from the switches and other boards. The display boards, mounting points, final standoff heights, and driver wiring still need designing and testing.

### Preset-channel display

I’ll use **two SC36-11SURKWA digits** for channels 1–20. Two bodies occupy **15 × 14 mm before spacing**, within the **22 × 17.5 mm preset window**. Package dimensions establish a preliminary fit; I still need to check digit alignment, brightness through the smoked cover, mounting height, and physical clearances.

I’ll finalize the display-driver arrangement and suitable 3.3 V-to-5 V logic buffering for the Teensy before completing the display PCB design.

### DCS-BIOS display brightness and panel backlighting

I’ll have **DCS-BIOS control both the seven-segment display brightness and the panel backlighting**. For the A-10C/A-10C II, the initial mapping is the exported **`INT_CONSOLE_L_BRIGHT` (Console Light Brightness)** value from the [DCS-BIOS A-10C module](https://github.com/DCS-Skunkworks/dcs-bios/blob/main/Scripts/DCS-BIOS/lib/modules/aircraft_modules/A-10C.lua). I still need to verify its behavior in DCS, including aircraft electrical power and lighting-off conditions.

- **Display brightness:** The Teensy will set the intensity registers on both MAX7219 drivers. Each driver has 16 intensity levels; firmware will use shutdown for a fully dark display. Both display windows will follow the cockpit lighting level, with a separately adjustable display brightness curve.
- **Panel backlighting:** I’ll reserve one PWM-capable Teensy GPIO for a low-side N-channel MOSFET driver. The MOSFET must be specified for operation at a 3.3 V gate drive, with a gate resistor and gate-to-ground pull-down. The 5 V LED branches will have suitable current-limiting resistors. LED current will come from the external supply, not from a Teensy GPIO. Firmware will use a separate backlight brightness curve.
- **Power and connections:** A reusable distribution board will accept user-supplied regulated 5 V DC and distribute it to the panels. The panel’s MOSFET circuit will control its own backlighting; the distribution board will not regulate voltage or control brightness. Grounds will be shared, and external 5 V must not backfeed USB/VUSB. The display sub-board will carry both MAX7219 drivers, their current-setting and decoupling parts, and suitable 3.3 V-to-5 V logic buffering.
- **Light shielding:** I’ll design a 3D-printed opaque light shield around the display windows to prevent panel-backlight spill from washing out the seven-segment displays.
- **Startup and testing:** Firmware will start with both lighting outputs off until initialized. I still need to finalize the GPIO, MOSFET, LED quantities, resistor values, connectors, power budget, DCS mapping, and connection-loss behavior, then test dimming, flicker, heat, and light leakage.

This is an approved design requirement; the lighting schematic, PCB layout, and firmware are still to be implemented and tested.

## Frequency controls

**The current design uses rotary encoders for all five frequency controls.** I’m also investigating a rotary-switch alternative after asking PC Flights about enlarged FREQ holes in both panel layers and anti-rotation slots in the clear backing panel. See the [November 6 development update](#development-update--november-6-2026) for PC Flights’ quote and my request for a stocked option. **I’ll revisit the rotary-switch version after completing the ARC-186 and ARC-210 v2.0 projects.** It will still need further mechanical and electrical design and testing.

I originally planned to use frequency rotary switches, but I’ve restored my original ARC-164 encoder KiCad project and will check its fit, clearances, and wiring before continuing the design. The **A11015RNCQ switches were the wrong parts for the ARC-164**. I’ve requested cancellation from DigiKey; **if the order is not canceled, I’ll keep them as parts for ARC-210 V2**.

MAIN and PRESET use **C&K A12505RNCQ rotary switches with 12.7 mm actuators**. VOL uses the same **PEC11R-4230F-S0024 with a 30 mm shaft** as the FREQ encoders, and the channel control remains a rotary encoder. The final knob fit and mounting clearances still need testing.

## VOL rotary encoder selection

I’ve selected the **Bourns PEC11R-4230F-S0024** for VOL, matching the FREQ and channel encoders. It has a **30 mm long, 6 mm diameter flatted shaft**, **24 detents, 24 pulses per revolution, PCB terminals, and a momentary push switch**. I’ll buy these from [Mouser, part 652-PEC11R-4230F-S24](https://www.mouser.com/en/ProductDetail/Bourns/PEC11R-4230F-S0024?qs=Zq5ylnUbLm6MC5h%2FLr6Brg%3D%3D).

I plan to make the VOL knob with a sleeve that extends through the **10 mm panel hole** to reach the encoder shaft, with clearance so it turns freely. Knob engagement and the mounting arrangement still need physical test fitting.

## TONE, SQL, and STATUS controls

I plan to use a **spring-loaded momentary toggle for TONE**: hold it to activate the tone, then release it to return to OFF. **I still need to select the exact TONE and SQL switches** and check their operation, travel, mounting dimensions, and clearance behind the faceplate.

For **STATUS**, I plan to use a **normally open momentary pushbutton, not a light**. The contacts close while the button is pressed and open again when it is released.

## Assembly tool note

I use **10 mm and 13 mm deep-well sockets** to tighten the **mounting nuts on the rotary switches and encoders**. Use whichever socket fits each nut; the deep well provides clearance over the shaft.

## MAIN and PRESET rotary switches

**Panel and fit checks — November 3, 2026:** I’ve physically test-fitted the **C&K A12505RNCQ for MAIN** and confirmed that it fits and works for this control. I also checked the panel and confirmed that **PRESET is 45° per position**, so I’ll use the **C&K A12505RNCQ with the stop ring set to 3 positions** for **MNL–PRESET–GRD**, giving **90° total travel**. PRESET’s final mounting and shaft engagement still need checking. PCB electrical and DCS integration testing are still to be completed.

I plan to use **two C&K A12505RNCQ rotary switches**, one for MAIN and one for PRESET. These are eight-position switches with the shorter **12.7 mm (0.5-inch) flatted actuator**, **PCB through-hole terminals**, and **45° indexing**. See the [C&K A Series datasheet](https://www.ckswitches.com/media/1349/arotary.pdf).

I plan to mount **both switches directly on the Main PCB, with their resistor ladders on the same board**. I’ll secure MAIN and PRESET mechanically using their **threaded bushings, mounting nuts, and anti-rotation alignment holes**. The **PCB pins will provide the electrical connections**, rather than serving as the primary mechanical support. I’ll check the mounting stack and board spacing so tightening the nuts does not strain the pins or bend the Main PCB. This will avoid separate rotary-switch PCBs and the wiring between those boards and the Main PCB. I’ll use the ARC-210 switch circuit and footprint as a starting point, then check the pin assignments, component placement, and analog readings for this layout.

| Control | Part number | Stop-ring setting | Total travel |
| --- | --- | --- | --- |
| MAIN: OFF–MAIN–BOTH–ADF | **C&K A12505RNCQ** | Limit the switch to **4 positions** | **135°** |
| PRESET: MNL–PRESET–GRD | **C&K A12505RNCQ** | Limit the switch to **3 positions** | **90°** |

**MAIN and PRESET use the same switch: C&K A12505RNCQ. Only the stop-ring setting differs: 4 positions for MAIN and 3 positions for PRESET.**

I’ll set each stop ring before mounting the switch and check that it stops at the first and last labeled positions. Each click is **45°**.

**Shaft-height check:** The A12505RNCQ’s 12.7 mm actuator specification is not its complete PCB-to-tip height. This shorter switch does not meet the earlier 38.1 mm PCB-to-tip target in the proposed mounting arrangement; do not trim it to that target. The stock A12505RNCQ has now been test-fitted and confirmed for MAIN. I still need to check PRESET with the PCB, faceplate, mounting hardware, and knob and confirm its board spacing and shaft engagement before final assembly.

Two A12505RNCQ switches are needed for MAIN and PRESET. The [recorded component costs](#recorded-component-costs) retain my earlier A12515RNCQ purchase as purchase history; they do not record a purchase of these shorter replacements.

## Channel control

I’ll use a rotary encoder for the channel control. Its mounting still needs design and testing.

## USB connections and powered hubs

[Read about the USB connection plan and purchased powered hubs](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/USB-Connections-and-Powered-Hubs.md) for why I am using USB instead of RS-485.

## DCS-BIOS

I use [DCS-Skunkworks DCS-BIOS](https://github.com/DCS-Skunkworks/dcs-bios) to exchange control and display information with DCS, and [TekConnect](https://github.com/tekcreations/TekConnect) to manage my USB connections.

ARC-164 firmware, radio mappings, setup instructions, and any required export changes still need to be developed and tested. I’ll document the steps here as they become available.

## Physical radio panels and possible future support

I’m focusing future support on aircraft with a **physical radio control panel** that matches my hardware, so the panel will be useful to builders flying those aircraft. I’ll compare the controls and displays as well as the radio model. The A-10C/A-10C II remain my intended targets; the candidates below still need their own mappings and testing before I can support them.

| Aircraft | Physical panel | Future-support assessment |
| --- | --- | --- |
| F-16C Viper | ARC-164 UHF backup control panel | **Strongest next candidate.** The PC Flights faceplate used here reproduces this panel. Operation requires the aircraft's C&I selector in BACKUP. |
| F-5E Tiger II | Dedicated ARC-164 control panel | **Worth investigating.** Compare control positions, functions, and display behavior before committing to support. |
| C-101EB | Dedicated ARC-164 control panel | **Worth investigating.** Its layout and available functions differ, so hardware and firmware compatibility must be checked. |
| F-4E Phantom II | Dedicated UHF radio controls | **Lower priority; panel comparison required.** Its control arrangement differs substantially, so the presence of the radio alone does not establish a useful match for this build. |

References: [F-16C manual](https://www.digitalcombatsimulator.com/en/downloads/documentation/filter/aircraft-is-f-16c/apply/), [F-5E manual](https://www.digitalcombatsimulator.com/upload/iblock/528/DCS%20F-5%D0%95-3%20Flight%20Manual_ENG.pdf), [C-101 cockpit guide](https://assets.chucksguides.com/pdf/DCS%20C-101CC%20Guide.pdf), and [F-4E cockpit guide](https://assets.chucksguides.com/aircraft/dcs/f-4e/0221930c6152572a4cc36908ded30c59/46.page.html).

**Each additional aircraft would need separate DCS-BIOS mappings, firmware integration, and testing.** Control inputs, display outputs, operating modes, and DCS-BIOS coverage must be checked for that module. These are investigation priorities, not compatibility claims or release commitments.

## Related radio projects

- [A-10-Sim repository](https://github.com/dgdimick/A-10-Sim) — my collection of A-10C II cockpit panel projects.
- [ARC-210 radio panel](https://github.com/dgdimick/ARC-210-DCS-Display) — my other radio panel project.
- [ARC-186 COMM-VHF radio panel](https://github.com/dgdimick/ARC-186-DCS-Display) — my planned VHF panel with its own Teensy 4.1 and USB connection.

## A central directory for SIMPIT builders

I’d love to see a central GitHub directory linking to other SIMPIT builders’ projects, with files and credit staying with each builder. This is an idea, not a project I’ve committed to building.

[Read more about the directory idea](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/Future-Thoughts.md#a-central-directory-for-simpit-builders). If you know of one or would like to discuss it, let me know in [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions).

## Sharing code and improvements

I plan to share this panel’s main firmware source under the [MIT License](https://github.com/dgdimick/ARC-164-DCS-Display/blob/main/Docs/LICENSE-MIT.txt). The firmware is still being developed, and I’m happy to share available work with anyone who asks.

If you adapt my code or add improvements, I’d love to work with you and bring useful changes back into the project so other builders—and my other panel projects—can benefit too. Please share your changes through a pull request or get in touch in [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions). Contributing changes back is welcome, but it isn’t an extra condition of the MIT License. Third-party code keeps its own license.

## Questions and community builds

**Planning a build, already working on one, or just looking around?** Tell me which panel interests you and what you fly in [GitHub Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions). Questions, ideas, and progress photos are welcome—even if you haven’t started yet. If you get stuck, ask away—I’m happy to help where I can.

If you’re local to me in **New Mexico, USA**, I’d be happy to meet up and provide whatever help I can with your SIMPIT. Get in touch through [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions) so we can talk about your build and arrange a time.

I welcome bug reports from anyone using the project—**even tiny bugs are worth reporting**. If something doesn’t work as expected, please let me know in the [Bugs discussion section](https://github.com/dgdimick/ARC-164-DCS-Display/discussions/categories/bugs). Tell me which firmware version and board revision you’re using, if applicable, what you did, what you expected, and what happened. Reports about the build instructions are welcome too. Your reports help me improve the project for everyone.

## PC Flights affiliation

I am not affiliated with [PC Flights](https://pcflights.com/) in any way. I simply chose to use their panels for my own cockpit projects. PC Flights has supplied me with a drawing file to assist with the Button PCB layout.

## Disclaimer

This is a hobby flight-simulation project, not equipment intended for use in real aircraft. Software, firmware, PCB designs, wiring information, and printable parts are provided "as is," without warranty, subject to their respective licenses.

Users are responsible for verifying compatibility, wiring, supply voltages, assembly, and safe operation before use. To the maximum extent permitted by applicable law, the authors and contributors disclaim liability for injury, equipment damage, data loss, or other losses arising from use of this project.

## Licensing

- **PCBs:** [CERN Open Hardware Licence Version 2 – Permissive (CERN-OHL-P-2.0)](https://github.com/dgdimick/ARC-164-DCS-Display/blob/main/Docs/LICENSE-CERN-OHL-P-2.0.txt)
- **Teensy firmware:** [MIT License](https://github.com/dgdimick/ARC-164-DCS-Display/blob/main/Docs/LICENSE-MIT.txt)
- **STL files:** [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://github.com/dgdimick/ARC-164-DCS-Display/blob/main/Docs/LICENSE-CC-BY-4.0.txt)

Copies of the applicable licenses are included in the [Docs directory](https://github.com/dgdimick/ARC-164-DCS-Display/tree/main/Docs). Firmware and printable parts are still under development; these license terms do not mean those files have been released. Third-party code, libraries, and models retain their own licenses.

---

[**My Mission Statement — Why I Build and Share These Projects**](https://github.com/dgdimick/A-10-Sim/blob/master/Mission-Statement.md)
