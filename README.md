# ARC-164 Radio Panel for DCS

**Last updated: November 3, 2026 at 7:49 AM MST (America/Denver)**
<!-- Refresh this timestamp whenever this README changes; use the actual current America/Denver date and time with the correct MST/MDT abbreviation. -->

<p align="center">
  <img src="images/ARC-164_uhf_panel.jpg" width="500" alt="ARC-164 UHF radio panel reference photo">
</p>

*Panel reference photo: PC Flights.*

I’m developing the hardware and firmware for my ARC-164 radio panel.

## Current development order

For these two radio panels, I plan to build and test the **ARC-164**, followed by the **ARC-186**, then investigate additional aircraft support with matching physical radio panels.

**This order may change based on user feedback and interest.** These are plans, not fixed release dates.

## Other SIMPIT panels

Once I’ve finished the radio panels, I plan to build other panels for my SIMPIT, including the **SAS and emergency trim panels**. I’ll share those projects as they develop. These are future plans.

## Through-hole components

While I could use surface-mount (SMD) parts to make the boards smaller, I plan to use through-hole components to make the project easier for everyone to build and solder with basic tools.

I chose the listed component suppliers because I’m aiming for better-quality parts than I generally expect from generic Amazon listings, even if they cost a little more. Parts from Amazon may work, and I use some myself, but substitutes may have different dimensions or pin spacing and may not fit the PCBs I designed for this project. Please compare the exact part specifications and PCB footprint before buying a substitute.

## Recorded component costs

These are my recorded purchases so far, in **US dollars**. The total includes rotary switches bought before I returned to frequency encoders; it is not a shopping list for the current design. The **A11015RNCQ switches are 10-position switches** and were the wrong parts for the ARC-164. I’ve requested cancellation from DigiKey; **if the order is not canceled, I’ll keep them as parts for ARC-210 V2**.

| Item | Quantity | Cost (USD) |
|---|---:|---:|
| QBSLDIW301GR white seven-segment LED digits | 10 | $17.43 |
| A12515RNCQ rotary switches — earlier long-shaft selection; no longer the current MAIN/PRESET choice | 5 | $55.66 |
| A11015RNCQ rotary switches — 10 positions; for ARC-210 V2 if DigiKey does not cancel the order | 3 | $35.07 |
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

**The VOL encoder isn’t included in the total yet.** I previously asked DigiKey to add a PEC11R-4230F-S0024, but I’ve since chosen the **PEC11H-4220F-S0024**, matching the FREQ encoders. I’ll confirm the order details before adding its actual cost to this purchase history.

**This total is before PCBs, display drivers, resistors, connectors, and the other remaining parts. It is not the complete build cost.** I’ll update the total as I buy the remaining parts. Additional shipping or fees not listed above are also excluded.

## DigiKey order sheet — rotary controls and LED digits

This is my order sheet for the rotary controls and LED digits for **one ARC-164 panel**, prepared **November 3, 2026**. It lists the full quantities needed; I’ll deduct any parts I already have before ordering.

| Quantity | Use | Manufacturer part number | DigiKey part number | Estimated unit price (USD) | Estimated total (USD) |
| ---: | --- | --- | --- | ---: | ---: |
| 7 | Five FREQ encoders, channel encoder, and VOL | [Bourns PEC11H-4220F-S0024](https://www.digikey.com/en/products/detail/bourns-inc/PEC11H-4220F-S0024/12349532) | 118-PEC11H-4220F-S0024-ND | $4.088 | $28.62 |
| 2 | MAIN and PRESET rotary switches | [C&K A12505RNCQ](https://www.digikey.com/en/products/detail/c-k/A12505RNCQ/2043159) | CKN10203-ND | $13.41 | $26.82 |
| 10 | White 0.3-inch common-cathode seven-segment LED digits | [QT Brightek QBSLDIW301GR](https://www.digikey.com/en/products/detail/qt-brightek-qtb/QBSLDIW301GR/22077720) | 1516-QBSLDIW301GR-ND | $1.743 | $17.43 |
| | **Estimated subtotal** | | | | **$72.87** |

All seven encoders in this order sheet have **20 mm shafts**. MAIN and PRESET use the **same A12505RNCQ switch**, with the stop ring set to **4 positions for MAIN** and **3 positions for PRESET**; both index at **45° per position**.

These are estimated DigiKey prices, using the quantity-five price tier for seven encoders the quantity-one tier for two switches, and the quantity-ten tier for ten LED digits. Prices can change; shipping, tax, and tariffs are excluded. This is an order-planning estimate, separate from my recorded purchases above.

**This is not the complete build BOM.** TONE, SQL, STATUS, display drivers, other display components, resistors, capacitors, connectors, PCBs, and the other remaining parts are not included in this sheet.

## Things that need to be completed

**Last updated: November 3, 2026 at 7:49 AM MST (America/Denver)**
<!-- Refresh this section timestamp whenever the work list changes, using the actual America/Denver time and MST/MDT. -->

This is my current work list for the hardware, firmware, testing, and build instructions.

1. **Panel layout and parts:** Confirm dimensions, mounting clearances, controls, and the complete parts list. **TONE and SQL switches:** Select the exact parts and verify their mounting dimensions, required operation and travel, and clearances before finalizing the PCB. Test-fit the selected [PC Flights six-digit frequency display](#frequency-display), including digit visibility and brightness through the smoked cover. **Choose the preset-channel display** for the 22 × 17.5 mm window, then check its dimensions, pinout, mounting height, and clearance.
2. **PCB and schematic design:** Use rotary encoders for all five frequency controls, with no frequency-switch resistor ladders. Design the Main PCB with the MAIN and PRESET rotary switches, their resistor ladders, controller, and display circuitry. Check the restored frequency-encoder PCB and its connections to the Main PCB. Design the small display PCB and its standoff mounting, with the display soldered directly to the board; set the height after checking it against the faceplate. Finalize Teensy pin assignments, check the complete electrical design, and verify clearances and test fitting before ordering boards.
3. **Printed parts:** Design and test-fit the required knobs, brackets, and spacers with the selected hardware. Verify shaft engagement, knob retention, mounting height, and clearance behind the faceplate.
4. **DCS-BIOS mappings and any needed changes:** Check which inputs and display outputs are already available for this radio. Identify missing data, make any necessary export changes, and document them. Check the correct ARC-164 radio instance for each intended A-10 variant.
5. **Firmware:** Write the control and display firmware and verify USB communication with DCS-BIOS.
6. **Bench and board testing:** Test the controls, displays, and power requirements together, then assemble and electrically test the manufactured boards.
7. **Dual ARC-164 support:** Integrate support for aircraft with two ARC-164 radios, such as the A-10C. I plan to use a single jumper on the Main PCB to select whether each panel operates as **Radio 1 or Radio 2**. Design the jumper input and firmware selection, verify the DCS-BIOS mappings for both radio instances, and test both panels together.
8. **Testing in DCS:** Check control operation, display updates, startup behavior, reconnection, and extended reliability with the intended aircraft and the other radio panels connected.
9. **Documentation:** Publish assembly instructions, wiring diagrams, final parts and print quantities, PCB ordering files, firmware loading steps, DCS-BIOS setup requirements, and troubleshooting notes.
10. **Assembly pictures:** During assembly, take clear pictures of component placement, soldering, wiring, and mounting, including both sides of each PCB with the silkscreen markings visible. Add the pictures to the assembly instructions so other builders can follow along.


## Controller choice — Teensy 4.1

I’m using the **Teensy 4.1** for its compact size and room for the panel’s controls and displays. It runs at **600 MHz**, compared with **16 MHz for the classic Arduino Uno R3, Mega 2560, and ATmega328P Nano**. I still need to finalize the pin assignments. See the [Teensy specifications](https://www.pjrc.com/store/teensy41.html).

I’ll use USB for DCS-BIOS; Ethernet isn’t needed. The Teensy uses **3.3 V logic**, and its inputs are **not 5 V tolerant**, so I’ll design the display-driver connections accordingly.

## Seven-segment display plan

### Frequency display

I’ve chosen the [PC Flights six-digit 0.3-inch amber seven-segment display](https://pcflights.com/6-digits-7-segment-led-display-03-amber/) for frequency. Its drawing shows a **41 × 11 mm body, 5.8 mm thick**, with approximately **7.7 mm-tall digits**. It is **common cathode**, with a decimal point on every digit, so it can show a frequency such as **251.000**. The body fits within the **53.5 × 17.5 mm frequency window**. I still need to test brightness through the smoked cover and check the mounting, pinout, driver wiring, and clearance behind the faceplate.

<a href="images/PC-Flights-Six-Digit-Amber-Display-Drawing.png"><img src="images/PC-Flights-Six-Digit-Amber-Display-Drawing.png" width="350" alt="PC Flights six-digit amber display dimensions and common-cathode pinout drawing"></a>

*PC Flights display drawing. Click to enlarge the dimensions and pinout.*

### Display mounting

I’ll use a **small frequency-display PCB mounted on standoffs**, with the **display soldered directly to it**. I’ll set the standoff height during test fitting so the display sits at the correct height behind the faceplate window, with clearance from the switches and other boards. The driver circuitry can be connected by wires if it needs to sit elsewhere. The display PCB, mounting points, and final standoff height still need to be designed and tested.

### Preset-channel display — selection pending

**I still need to choose the two-digit channel display** for channels 1–20 behind the **22 × 17.5 mm window**. PC Flights offers [single-digit amber displays](https://pcflights.com/7-segment-led-display-03-amber/) and a [three-digit amber display](https://pcflights.com/3-digits-7-segment-led-display-03-amber/). I’ll check whether two single-digit displays fit side by side, or whether a three-digit package could show two digits with the unused digit left blank and hidden behind the faceplate. Neither arrangement is selected yet; package dimensions, pinout, digit alignment, mounting height, and brightness still need checking.

The earlier three-four-digit-block arrangement is no longer my display plan. I’ll finalize the channel display and driver arrangement before completing the display PCB and suitable 3.3 V-to-5 V logic buffering for the Teensy.

## Frequency controls

**I’m keeping rotary encoders for all five frequency controls, including future ARC-164 versions.** Fitting frequency rotary switches would require enlarging the holes and cutting anti-rotation alignment slots in the clear underpanel, so I won’t offer a frequency rotary-switch version.

I originally planned to use frequency rotary switches, but I’ve restored my original ARC-164 encoder KiCad project and will check its fit, clearances, and wiring before continuing the design. The **A11015RNCQ switches were the wrong parts for the ARC-164**. I’ve requested cancellation from DigiKey; **if the order is not canceled, I’ll keep them as parts for ARC-210 V2**.

MAIN and PRESET use **C&K A12505RNCQ rotary switches with 12.7 mm actuators**. VOL uses the same **PEC11H-4220F-S0024 with a 20 mm shaft** as the FREQ encoders, and the channel control remains a rotary encoder. The final knob fit and mounting clearances still need testing.

## VOL rotary encoder selection

I’ve selected the **Bourns PEC11H-4220F-S0024** for VOL, matching the FREQ encoders. It has a **20 mm long, 6 mm diameter flatted shaft**, **24 detents, 24 pulses per revolution, PCB terminals, and a momentary push switch**. See the [DigiKey listing](https://www.digikey.com/en/products/detail/bourns-inc/PEC11H-4220F-S0024/12349532).

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
