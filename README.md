# ARC-164 Radio Panel for DCS

**Last updated: October 31, 2026 at 1:08 AM MDT (America/Denver)**
<!-- Refresh this timestamp whenever this README changes; use the actual current America/Denver date and time with the correct MST/MDT abbreviation. -->

<p align="center">
  <img src="images/ARC-164_uhf_panel.jpg" width="500" alt="ARC-164 UHF radio panel reference photo">
</p>

*Panel reference photo: PC Flights.*

## Panel compatibility

I’ve purchased and checked the [PC Flights F-16C Viper UHF panel](https://pcflights.com/f-16c-viper-uhf-radio-control-home-cockpit-panel/) and confirmed it suits this A-10C II ARC-164 build. F-16C DCS-BIOS firmware support is a separate task.

## October 10, 2026 — Project update

I have almost completed the [ARC-210 project](https://github.com/dgdimick/ARC-210-DCS-Display), and I have ordered the **ARC-164 and ARC-184 faceplates**. Once the ARC-210 is finished and the new faceplates arrive, I can take a closer look at the next builds.

## My next project

My current plan is to work on the **AN/ARC-164 UHF radio panel** after completing the [A-10C2 ARC-210 implementation](https://github.com/dgdimick/ARC-210-DCS-Display). I may adjust that order based on user feedback and interest.

The plan is to build a physical ARC-164 panel for my DCS A-10C II cockpit, with working controls and a display linked to DCS through DCS-BIOS.

I’m using this page to share my plans as the project develops. I’m exploring display options and the panel layout while I finish the ARC-210. Firmware and the hardware design are still to come, and I’ll share a release date when I have one.

As development progresses, I will add build notes, hardware details, firmware, and photos here.

## Current development order

My current plan is to finish the **A-10C II (A-10C2) ARC-210 implementation**, then build and test the **ARC-164**, followed by the **ARC-186**. After those projects, I’ll return to additional aircraft support, starting with the **ARC-210 and C-130J**. I’m focusing on aircraft with a matching physical radio panel.

**This order may change based on user feedback and interest.** These are my current priorities, not fixed release dates.

## Other SIMPIT panels

Once I’ve finished the radio panels, I plan to build other panels for my SIMPIT, including the **SAS and emergency trim panels**. I’ll share those projects as they develop. These are future plans, and my priorities may change based on user feedback and interest.

## Through-hole components

While I could use surface-mount (SMD) parts to make the boards smaller, I plan to use through-hole components to make the project easier for everyone to build and solder with basic tools, following the same approach as my ARC-210 project.

## Things that need to be completed

**Last updated: October 30, 2026 at 11:19 PM MDT (America/Denver)**
<!-- Refresh this section timestamp whenever the work list changes, using the actual America/Denver time and MST/MDT. -->

This is my current work list. Hardware and firmware are still under development, and I haven’t set a release date.

1. **Panel layout and parts:** Confirm dimensions, mounting clearances, controls, display choices, and the complete parts list.
2. **PCB and schematic design:** Design the new PCB for all five frequency encoders and the preset-channel encoder, assuming there is room, along with the remaining controller and display circuitry. Finalize Teensy pin assignments and check the electrical design before ordering boards.
3. **Printed parts:** Design and test-fit the required knobs, brackets, and spacers with the selected hardware.
4. **DCS-BIOS mappings and any needed changes:** Check which inputs and display outputs are already available for this radio. Identify missing data, make any necessary export changes, and document them. Check the correct ARC-164 radio instance for each intended A-10 variant. The ARC-210 changes do not automatically apply to this panel.
5. **Firmware:** Write the control and display firmware and verify USB communication with DCS-BIOS.
6. **DCS bridge testing support:** Modify the DCS bridge to allow each panel to be tested independently.
7. **Bench and board testing:** Test the controls, displays, and power requirements together, then assemble and electrically test the manufactured boards.
8. **Testing in DCS:** Check control operation, display updates, startup behavior, reconnection, and extended reliability with the intended aircraft and the other radio panels connected.
9. **Documentation:** Publish assembly instructions, wiring diagrams, final parts and print quantities, PCB ordering files, firmware loading steps, DCS-BIOS setup requirements, and troubleshooting notes. Link to the shared [DCS-BIOS guide](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/DCS-BIOS.md) where the instructions already apply.
10. **Assembly pictures:** When my PCBs arrive and I start building, take clear pictures of component placement, soldering, wiring, and mounting, including both sides of each PCB with the silkscreen markings visible. Add the pictures to the assembly instructions so other builders can follow along.


## Controller choice — Teensy 4.1

I’m staying with the **Teensy 4.1** for the ARC-164. Its compact size makes it easier to fit behind the faceplate, it offers 42 readily accessible I/O pins, and it keeps the controller consistent with the ARC-210 project. The final ARC-164 pin allocation still needs to be verified.

The **Teensy 4.1 runs at 600 MHz**, compared with **16 MHz for the classic Arduino Uno R3, Mega 2560, and ATmega328P Nano** — **37.5 times the CPU clock frequency**. This provides processing headroom for display updates and controls; it is not a measured 37.5-times improvement in display refresh speed. See the [Teensy specifications](https://www.pjrc.com/store/teensy41.html) and [classic Arduino board comparison](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/Why-Teensy.md).

I considered the Arduino Due, but it is physically larger and would not save money at the prices checked on **October 30, 2026**: a genuine Due with headers was listed at **$49.40** at [DigiKey](https://www.digikey.com/en/products/detail/arduino/A000062/3712582), compared with **$31.50** for a Teensy 4.1 or **$35.95** with headers at [SparkFun](https://www.sparkfun.com/development-boards/microcontrollers/teensy/teensy-boards.html), before shipping and tax. These are reference prices, not fixed build costs.

Ethernet is not required for the planned USB DCS-BIOS connection. The Teensy 4.1 version without Ethernet is also an option; its listed price was **$29.60** at the same price check. Teensy 4.1 uses **3.3 V logic**, and its inputs are not 5 V tolerant, so display-driver connections must be designed accordingly. See the [PJRC specifications](https://www.pjrc.com/store/teensy41.html).

## Why I keep using Teensy 4.1s

[Read why I keep using Teensy 4.1s](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/Why-I-Keep-Using-Teensy-4.1s.md) for the consistency, processing speed, available pins, and cost comparison behind the controller choice.

## Encoder PCB plan

The ARC-164 will need a **new encoder PCB**, because its frequency-encoder positions do not line up with the ARC-210 encoder PCB. The plan is to mount **all five frequency encoders and the preset-channel encoder on one PCB**, assuming there is enough room and clearance behind the faceplate. The final board outline and encoder placement will be confirmed during the mechanical layout.

## Separate controllers for each radio

The **ARC-164 and ARC-186 will each use their own Teensy 4.1**, with a separate USB connection to DCS-BIOS for each panel. Either radio can be built and operated independently. Dedicated controllers keep each panel's wiring and firmware separate and leave room for future additions.

The ARC-164 controller will operate the ARC-164 only; the [ARC-186 COMM-VHF panel](https://github.com/dgdimick/ARC-186-DCS-Display) will have its own controller. Hardware, pin assignments, and firmware remain under development.

## My SIMPIT and test computer

[View my SIMPIT and test computer](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/My-SIMPIT-and-Test-Computer.md) for my computer configuration, monitors, and current USB setup. **This describes my own development and flight-simulation setup, not minimum requirements for the radio panels.**

## USB connections and powered hubs

[Read about the USB connection plan and purchased powered hubs](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/USB-Connections-and-Powered-Hubs.md) for why I am using USB instead of RS-485, GPIO availability, sharing a Teensy across smaller panels, and expansion using my existing cockpit USB setup.

## DCS-BIOS

[My step-by-step setup guide](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/DCS-BIOS.md) covers installation, file changes, and TekConnect—the app I use to manage my connections.

- [Patched A-10C.lua](https://raw.githubusercontent.com/dgdimick/ARC-210-DCS-Display/master/Docs/DCS-BIOS/A-10C.lua) — ARC-210 changes included; for **DCS-BIOS v0.11.8**.
- [DCS-BIOS-only Export.lua](https://raw.githubusercontent.com/dgdimick/ARC-210-DCS-Display/master/Docs/DCS-BIOS/DCS-BIOS-only/Export.lua) — for setups without WWT or SRS.

Follow the guide before replacing files. The ARC-210 patch does not add support for this planned radio.

## Physical radio panels and possible future support

I’m focusing future support on aircraft with a **physical radio control panel** that matches my hardware, so the panel will be useful to builders flying those aircraft. I’ll compare the controls and displays as well as the radio model. The A-10C/A-10C II remain my intended targets; the candidates below still need their own mappings and testing before I can support them.

| Aircraft | Physical panel | Future-support assessment |
| --- | --- | --- |
| F-16C Viper | ARC-164 UHF backup control panel | **Strongest next candidate.** The PC Flights faceplate used here reproduces this panel. Operation requires the aircraft's C&I selector in BACKUP. |
| F-5E Tiger II | Dedicated ARC-164 control panel | **Worth investigating.** Compare control positions, functions, and display behavior before committing to support. |
| C-101EB | Dedicated ARC-164 control panel | **Worth investigating.** Its layout and available functions differ, so hardware and firmware compatibility must be checked. |
| F-4E Phantom II | Dedicated UHF radio controls | **Lower priority; panel comparison required.** Its control arrangement differs substantially, so the presence of the radio alone does not establish a useful match for this build. |

References: [F-16C manual](https://www.digitalcombatsimulator.com/upload/iblock/3dc/5p9ejw7gi488n9zd15csrxxs8os2dflk/DCS_F-16C_Early_Access_Guide_EN.pdf), [F-5E manual](https://www.digitalcombatsimulator.com/upload/iblock/528/DCS%20F-5%D0%95-3%20Flight%20Manual_ENG.pdf), [C-101 cockpit guide](https://assets.chucksguides.com/pdf/DCS%20C-101CC%20Guide.pdf), and [F-4E cockpit guide](https://assets.chucksguides.com/aircraft/dcs/f-4e/0221930c6152572a4cc36908ded30c59/46.page.html).

**Each additional aircraft would need separate DCS-BIOS mappings, firmware integration, and testing.** Control inputs, display outputs, operating modes, and DCS-BIOS coverage must be checked for that module. These are investigation priorities, not compatibility claims or release commitments.

## Related radio projects

- [C-130J ARC-210 support in the main ARC-210 project](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/C-130J-Support.md) — planned reuse of my existing ARC-210 hardware with C-130J firmware, DCS-BIOS mappings, and menus. The same panel hardware should work with both the A-10C II and C-130J using the appropriate firmware and mappings; C-130J testing is pending.

Follow the [ARC-186 COMM-VHF radio panel project](https://github.com/dgdimick/ARC-186-DCS-Display) for its build plans using a dedicated Teensy 4.1 and its own USB connection.

## A central directory for SIMPIT builders

I’d love to see a central GitHub directory linking to projects from SIMPIT builders like me—a place to find panels, code, PCB designs, printable parts, and build guides for SIMPITs of every size. It could link back to each builder’s own repository so the files, updates, and credit stay with the original project. This is an idea I’d like to see happen, rather than a project I’ve committed to building myself.

[Read more about the directory idea](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/Future-Thoughts.md#a-central-directory-for-simpit-builders). If you know of one or would like to discuss it, let me know in [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions).

## Sharing code and improvements

I plan to share this panel’s main firmware source under the **MIT License**, following the same approach as my ARC-210 project, and I’m happy to provide my available code to anyone who asks. This panel’s firmware is still being developed; the [published ARC-210 source](https://github.com/dgdimick/ARC-210-DCS-Display/tree/master/Firmware/Source/Master_Program) is available now under its [MIT License](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/LICENSE-MIT.txt).

If you adapt my code or add improvements, I’d love to work with you and bring useful changes back into the project so other builders—and my other panel projects—can benefit too. Please share your changes through a pull request or get in touch in [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions). Contributing changes back is welcome, but it isn’t an extra condition of the MIT License. Third-party code keeps its own license.

## Questions and community builds

**Planning a build, already working on one, or just looking around?** Tell me which panel interests you and what you fly in [GitHub Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions). Questions, ideas, and progress photos are welcome—even if you haven’t started yet. If you get stuck, ask away—I’m happy to help where I can.

If you’re local to me in **New Mexico, USA**, I’d be happy to meet up and provide whatever help I can with your SIMPIT. Get in touch through [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions) so we can talk about your build and arrange a time.

I welcome bug reports from anyone using the project—**even tiny bugs are worth reporting**. If something doesn’t work as expected, please let me know in the [Bugs discussion section](https://github.com/dgdimick/ARC-164-DCS-Display/discussions/categories/bugs). Tell me which firmware version and board revision you’re using, if applicable, what you did, what you expected, and what happened. Reports about the build instructions are welcome too. Your reports help me improve the project for everyone.

## PC Flights affiliation

I am not affiliated with [PC Flights](https://pcflights.com/) in any way. I simply chose to use their panels for my own cockpit projects.
