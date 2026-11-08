# ARC-164 three-board wiring — Version 1.0 prototype

**Last updated: November 8, 2026 at 10:44 AM MST (America/Denver)**

**PCB ordering is on hold: the J20 cable connector does not clear the Main Board.** I need to redesign **both the Main Board and LED Sub Board** to provide enough connector and cable clearance before ordering. I’ll **keep the tested LED positions, 0.75 mm gaps and 6 mm display-body height unchanged** while revising the connector area. The LED alignment and 8 mm mounting-stack fit passed, but the complete assembly does not yet clear the cable connector. I still need to test-fit the revised boards with the actual connector and cable before ordering; assembled electrical testing also remains pending.

This supersedes the earlier two-board, 32-pin, direct-stacking and sub-board Channel-encoder instructions. These are prototype hardware files; assembled electrical operation and the complete mechanical stack have not been verified.

## Board functions

| Board | Components and function |
| --- | --- |
| Main Board | Five FREQ encoders, Channel and VOL encoders, MAIN/PRESET rotary switches, wired-switch solder pads SW10–SW14, 19 green backlight LEDs D1–D19 with individual 330 ohm resistors R1–R19. J10 controls cable; J21 backlight feed; J22 auxiliary current-limited backlight landing. |
| Power Driver Board | U1 Teensy 4.1, U11/U12 MAX7219, U13 74AHCT125 5V buffer, Q1 IRLZ44N backlight MOSFET, supporting parts, J11 power jack, and J10/J20/J21. |
| LED Subboard | Six frequency digits DS1–DS6 and two preset digits DS7/DS8, SC36-11SURKWA common-cathode. J20 display cable. No encoder or panel-backlight LEDs. |

## Cable connections

| Cable | Connects | Wiring |
| --- | --- | --- |
| J10 CONTROLS | Main Board J10 to Power Driver Board J10 | 40 contacts, 2x20, 2.54mm pitch; same pin number at each end. |
| J20 DISPLAYS | Power Driver Board J20 to LED Subboard J20 | 40 contacts, 2x20, 2.54mm pitch; same pin number at each end. |
| J21 BACKLIGHT | Power Driver Board J21 to Main Board J21 | 3 contacts, 2.54mm pitch: 1 LED_5V; 2 BACKLIGHT_RETURN; 3 GND. |

J10 and J20 use unshrouded male headers and female-female ribbon cables, not direct board-to-board stacking. The planned J10 cable is about 3–4 inches; J20 is about 6 inches /150mm (Adafruit 1988). Exact short J10 cable and J21 cable/housing selection remain to be finalized. Samtec TSW-120-07-L-D is the selected 40-pin male header. Header orientation differs between board faces: follow pin numbers, not drawing left/right. Check actual cable continuity pin 1 to pin 1. Mark both cable ends CONTROLS/J10 or DISPLAYS/J20. The headers are not mechanically keyed; labels and different cable lengths do not prevent an incorrect connection. Connect Main Board first, then connect and lay the LED Subboard over it.

Never swap J10 and J20. Never connect J21 pin 2 directly to GND: it is the switched LED return, not a permanent ground.

## Power

J11 is the PJ-102AH edge-mounted barrel jack: center contact/pin 1 LED_5V (+), sleeve/pin 2 GND (−), switched contact/pin 3 unused. Supply regulated 5V DC ONLY using a 5.5mm outer /2.1mm inner center-positive plug. The board does not step down a higher voltage. Suggested supply: Mean Well GST25A05-P1J, 5V 4A; another well-regulated 5V supply (+/−5% or better) with enough current and the correct plug/polarity can be used.

The Teensy remains USB powered. External LED_5V is not connected to Teensy VIN or VUSB; all three boards share GND through the documented connections. J20 pins 29–32 are reserved supply/return contacts on the passive LED Subboard, not a backlight population. J22 on Main Board provides LED_5V and BACKLIGHT_RETURN for auxiliary resistor-limited branches.

## Backlight and display brightness

Each Main Board backlight branch is LED_5V -> 330 ohm resistor -> LED anode (pad 2); LED cathode (pad 1) -> BACKLIGHT_RETURN. Nineteen branches draw roughly 160mA at full brightness using a typical 2.2V LED drop; measure actual current when assembled. GPIO9 drives U13’s fourth buffer then R13 and Q1’s gate for PWM dimming. MAX7219 intensity settings control seven-segment brightness separately. No external 5V signal goes directly to a Teensy GPIO.

## Mechanical stack

**The LED positions on the v1.1 mockup passed my 100% print and physical alignment test behind the faceplate**, including the **0.75 mm LED gaps**, **6 mm display bodies**, and **8 mm mounting stack**. In the final adjustment, I moved the **channel LEDs 1 mm right** and the **FREQ LEDs 0.5 mm left** from the previous test layout. Each of the four mounts uses a **20 mm screw, a 6 mm-thick nut and two 1 mm washers**. **Assembled electrical testing remains to be done.**

I currently have **13.5 mm between the panel and Main Board**. I may use **14 mm** to let the LEDs sit slightly farther back from the glass. I’ll check the spacing when the manufactured PCBs arrive and add an extra spacer if needed. The LED Sub-Board mounts above the Main Board: its bottom connects to the Main Board’s top. I use **four Sub-Board mounts**, each with a **20 mm screw, a 6 mm-thick nut, and two 1 mm-thick washers**, giving **8 mm spacing** between the Main Board and LED Sub-Board. Main-to-LED mounting-hole alignment is face-up, without mirroring. The Power Driver Board mounts below the Main Board, **components facing down**, using **10 standoffs, each longer than 20 mm**. Choose the exact length to clear IC sockets, Teensy socket/header height, jack and cables. Model placement does not establish installed socket height.

D17 was moved clear of the MAIN switch SW7 courtyard before the final Main Board reroute. All three boards now pass DRC with zero violations and no unconnected items. The saved component positions, outline and holes were preserved during routing. Physical assembly and complete stack-height checks are still required.

## Control inputs and firmware

SW10=TONE, SW11=SQL, SW12=LOAD, SW13=TEST DISPLAY, SW14=STATUS. Each wired-switch pair has a signal pad and GND. SW7 MAIN uses four direct contacts; SW8 PRESET uses three direct contacts. No resistor ladders are used for those inputs. Enable Teensy 3.3V internal pull-ups. GPIO labels are not KiCad symbol pin numbers; see the table below.

No tested ARC-164 firmware is included in this PCB-only package. Firmware must implement this exact control map, MAX7219 chain/scan limits and brightness controls before powered functional testing. U11 uses six digits (scan limit 5); U12 uses two digits (scan limit 1), with digit indices starting at zero. Verify current limits and brightness on the assembled prototype.

## J10 pinout

| Pin | Signal |
| ---: | --- |
| 1 | GND |
| 2 | NC |
| 3 | NC |
| 4 | NC |
| 5 | NC |
| 6 | FREQ1_A |
| 7 | FREQ1_B |
| 8 | FREQ2_A |
| 9 | FREQ2_B |
| 10 | FREQ3_A |
| 11 | FREQ3_B |
| 12 | FREQ4_A |
| 13 | FREQ4_B |
| 14 | FREQ5_A |
| 15 | FREQ5_B |
| 16 | CHANNEL_A |
| 17 | CHANNEL_B |
| 18 | VOL_A |
| 19 | VOL_B |
| 20 | MAIN_POS1 |
| 21 | MAIN_POS2 |
| 22 | MAIN_POS3 |
| 23 | MAIN_POS4 |
| 24 | PRESET_POS1 |
| 25 | PRESET_POS2 |
| 26 | PRESET_POS3 |
| 27 | TONE |
| 28 | SQL |
| 29 | LOAD |
| 30 | TEST_DISPLAY |
| 31 | STATUS |
| 32 | GND |
| 33 | NC |
| 34 | NC |
| 35 | NC |
| 36 | NC |
| 37 | NC |
| 38 | NC |
| 39 | NC |
| 40 | NC |

## J20 pinout

| Pin | Signal |
| ---: | --- |
| 1 | SEG1_A |
| 2 | SEG1_B |
| 3 | SEG1_C |
| 4 | SEG1_D |
| 5 | SEG1_E |
| 6 | SEG1_F |
| 7 | SEG1_G |
| 8 | SEG1_DP |
| 9 | DIG1_0 |
| 10 | DIG1_1 |
| 11 | DIG1_2 |
| 12 | DIG1_3 |
| 13 | DIG1_4 |
| 14 | DIG1_5 |
| 15 | SEG2_A |
| 16 | SEG2_B |
| 17 | SEG2_C |
| 18 | SEG2_D |
| 19 | SEG2_E |
| 20 | SEG2_F |
| 21 | SEG2_G |
| 22 | SEG2_DP |
| 23 | DIG2_0 |
| 24 | DIG2_1 |
| 25 | NC |
| 26 | NC |
| 27 | GND |
| 28 | GND |
| 29 | LED_5V |
| 30 | LED_5V |
| 31 | BACKLIGHT_RETURN |
| 32 | BACKLIGHT_RETURN |
| 33 | NC |
| 34 | NC |
| 35 | NC |
| 36 | NC |
| 37 | NC |
| 38 | NC |
| 39 | NC |
| 40 | NC |

## J21 pinout

| Pin | Signal |
| ---: | --- |
| 1 | LED_5V |
| 2 | BACKLIGHT_RETURN |
| 3 | GND |

## Teensy input/output map

| Teensy GPIO | KiCad U1 pin | Signal |
| ---: | ---: | --- |
| 0 | 2 | FREQ1_A |
| 1 | 3 | FREQ1_B |
| 2 | 4 | FREQ2_A |
| 3 | 5 | FREQ2_B |
| 4 | 6 | FREQ3_A |
| 5 | 7 | FREQ3_B |
| 6 | 8 | FREQ4_A |
| 7 | 9 | FREQ4_B |
| 8 | 10 | FREQ5_A |
| 9 | 11 | BACKLIGHT_PWM_3V3 |
| 10 | 12 | DISP_LOAD_3V3 |
| 11 | 13 | DISP_DATA_3V3 |
| 12 | 14 | FREQ5_B |
| 13 | 35 | DISP_CLK_3V3 |
| 14 | 36 | CHANNEL_A |
| 15 | 37 | CHANNEL_B |
| 16 | 38 | VOL_A |
| 17 | 39 | VOL_B |
| 18 | 40 | MAIN_POS1 |
| 19 | 41 | MAIN_POS2 |
| 20 | 42 | MAIN_POS3 |
| 21 | 43 | MAIN_POS4 |
| 22 | 44 | PRESET_POS1 |
| 23 | 45 | PRESET_POS2 |
| 24 | 16 | PRESET_POS3 |
| 25 | 17 | TONE |
| 26 | 18 | SQL |
| 27 | 19 | LOAD |
| 28 | 20 | TEST_DISPLAY |
| 29 | 21 | STATUS |

The 83 J10/J20/J21 contacts were compared between mating boards, including unused contacts. PCB pads match the schematics. These checks do not replace testing actual cable assemblies.
