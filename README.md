# ARC-164 Radio Panel for DCS

**Last updated: October 31, 2026 at 9:52 PM MDT (America/Denver)**
<!-- Refresh this timestamp whenever this README changes; use the actual current America/Denver date and time with the correct MST/MDT abbreviation. -->

> **Disclaimer:** This hobby flight-simulation project is provided without warranty, subject to its licenses. Read the [full disclaimer](#disclaimer) before building or using it.

<p align="center">
  <img src="images/ARC-164_uhf_panel.jpg" width="500" alt="ARC-164 UHF radio panel reference photo">
</p>

*Panel reference photo: PC Flights.*

## Panel compatibility

I’ve purchased and checked the [PC Flights F-16C Viper UHF panel](https://pcflights.com/f-16c-viper-uhf-radio-control-home-cockpit-panel/) and confirmed it suits this A-10C II ARC-164 build. F-16C DCS-BIOS firmware support is a separate task.

## Current development order

For these two radio panels, I plan to build and test the **ARC-164**, followed by the **ARC-186**, then investigate additional aircraft support with matching physical radio panels.

**This order may change based on user feedback and interest.** These are plans, not fixed release dates.

## Other SIMPIT panels

Once I’ve finished the radio panels, I plan to build other panels for my SIMPIT, including the **SAS and emergency trim panels**. I’ll share those projects as they develop. These are future plans, and my priorities may change based on user feedback and interest.

## Through-hole components

While I could use surface-mount (SMD) parts to make the boards smaller, I plan to use through-hole components to make the project easier for everyone to build and solder with basic tools.

## Things that need to be completed

**Last updated: October 31, 2026 at 6:07 PM MDT (America/Denver)**
<!-- Refresh this section timestamp whenever the work list changes, using the actual America/Denver time and MST/MDT. -->

This is my current work list. Hardware and firmware are still under development, and I haven’t set a release date.

1. **Panel layout and parts:** Confirm dimensions, mounting clearances, controls, display choices, and the complete parts list.
2. **PCB and schematic design:** I’ve published the [encoder PCB and schematic v1.1](PCBs/Rotary%20Encoders/) with all five frequency encoders and the preset-channel encoder on one routed board. Version 1.1 fixes the copper-pour issue by removing an extra unassigned copper zone and refilling the GND pour. I still need to check clearances and test-fit it behind the faceplate before ordering boards. Design the remaining controller and display circuitry, finalize Teensy pin assignments, and check the complete electrical design.
3. **Printed parts:** Design and test-fit the required knobs, brackets, and spacers with the selected hardware.
4. **DCS-BIOS mappings and any needed changes:** Check which inputs and display outputs are already available for this radio. Identify missing data, make any necessary export changes, and document them. Check the correct ARC-164 radio instance for each intended A-10 variant.
5. **Firmware:** Write the control and display firmware and verify USB communication with DCS-BIOS.
6. **DCS bridge testing support:** Modify the DCS bridge to allow each panel to be tested independently.
7. **Bench and board testing:** Test the controls, displays, and power requirements together, then assemble and electrically test the manufactured boards.
8. **Testing in DCS:** Check control operation, display updates, startup behavior, reconnection, and extended reliability with the intended aircraft and the other radio panels connected.
9. **Documentation:** Publish assembly instructions, wiring diagrams, final parts and print quantities, PCB ordering files, firmware loading steps, DCS-BIOS setup requirements, and troubleshooting notes.
10. **Assembly pictures:** When my PCBs arrive and I start building, take clear pictures of component placement, soldering, wiring, and mounting, including both sides of each PCB with the silkscreen markings visible. Add the pictures to the assembly instructions so other builders can follow along.


## Controller choice — Teensy 4.1

I’m staying with the **Teensy 4.1** for the ARC-164. Its compact size makes it easier to fit behind the faceplate, it offers 42 readily accessible I/O pins. The final ARC-164 pin allocation still needs to be verified.

The **Teensy 4.1 runs at 600 MHz**, compared with **16 MHz for the classic Arduino Uno R3, Mega 2560, and ATmega328P Nano** — **37.5 times the CPU clock frequency**. This provides processing headroom for display updates and controls; it is not a measured 37.5-times improvement in display refresh speed. See the [Teensy specifications](https://www.pjrc.com/store/teensy41.html).

I considered the Arduino Due, but it is physically larger and would not save money at the prices checked on **October 30, 2026**: a genuine Due with headers was listed at **$49.40** at [DigiKey](https://www.digikey.com/en/products/detail/arduino/A000062/3712582), compared with **$31.50** for a Teensy 4.1 or **$35.95** with headers at [SparkFun](https://www.sparkfun.com/development-boards/microcontrollers/teensy/teensy-boards.html), before shipping and tax. These are reference prices, not fixed build costs.

Ethernet is not required for the planned USB DCS-BIOS connection. The Teensy 4.1 version without Ethernet is also an option; its listed price was **$29.60** at the same price check. Teensy 4.1 uses **3.3 V logic**, and its inputs are not 5 V tolerant, so display-driver connections must be designed accordingly. See the [PJRC specifications](https://www.pjrc.com/store/teensy41.html).

## Current PCBs

[View the current PCB versions and design files](PCBs/README.md).

## Encoder PCB plan

<a href="images/ARC-164-Encoder-PCB.png"><img src="images/ARC-164-Encoder-PCB.png" width="350" alt="ARC-164 Encoder PCB shown in KiCad with all six encoders"></a>

*ARC-164 Encoder PCB — KiCad 3D view. Click to enlarge. Clearance checks and test fitting are still pending.*

I’ve placed **all five frequency encoders and the preset-channel encoder on one PCB** designed for this faceplate.

My initial check of the supplied faceplate DXF suggests that a single **L-shaped PCB** is feasible: one section across the five frequency encoders, with an extension up the right side to the channel encoder. Assuming the drawing is in millimeters:

- The faceplate measures **146 × 123.8 mm**.
- The five frequency encoders are spaced **26 mm center to center**.
- The channel encoder is approximately **53.6 mm above** the frequency row and almost aligned with the rightmost frequency encoder.

**I still need to check the clearances** for the encoder bodies and solder pins, the nearby switch beside the vertical section, display hardware, connectors, and PCB mounting points. The vertical section may need a notch or a narrower connecting strip. The DXF does not declare its units, so I also need to confirm its scale against the actual faceplate before finalizing the design or ordering boards.

I’ve published the [encoder PCB and schematic v1.1](PCBs/Rotary%20Encoders/). All six encoders are placed on one board, and the latest saved layout is routed with a GND pour. **Version 1.1 fixes the isolated-copper issue:** I removed an extra unassigned copper zone that was overriding the GND pour, then refilled it. Fresh electrical checks reported zero violations, zero unconnected items, and zero schematic/PCB parity issues under the saved project settings. **I still need to check clearances and test-fit the board behind the faceplate; this is not a manufacturing release.** The faceplate drawing and its reference geometry are not included.

## Separate controllers for each radio

The **ARC-164 and ARC-186 will each use their own Teensy 4.1**, with a separate USB connection to DCS-BIOS for each panel. Either radio can be built and operated independently. Dedicated controllers keep each panel's wiring and firmware separate and leave room for future additions.

The ARC-164 controller will operate the ARC-164 only; the [ARC-186 COMM-VHF panel](https://github.com/dgdimick/ARC-186-DCS-Display) will have its own controller. Hardware, pin assignments, and firmware remain under development.

## USB connections and powered hubs

I plan to connect the ARC-164 directly by USB through powered hubs. I already use USB for my other SIMPIT equipment and have run 12 devices through one hub without issues. Each radio will have its own Teensy and USB connection.

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

References: [F-16C manual](https://www.digitalcombatsimulator.com/upload/iblock/3dc/5p9ejw7gi488n9zd15csrxxs8os2dflk/DCS_F-16C_Early_Access_Guide_EN.pdf), [F-5E manual](https://www.digitalcombatsimulator.com/upload/iblock/528/DCS%20F-5%D0%95-3%20Flight%20Manual_ENG.pdf), [C-101 cockpit guide](https://assets.chucksguides.com/pdf/DCS%20C-101CC%20Guide.pdf), and [F-4E cockpit guide](https://assets.chucksguides.com/aircraft/dcs/f-4e/0221930c6152572a4cc36908ded30c59/46.page.html).

**Each additional aircraft would need separate DCS-BIOS mappings, firmware integration, and testing.** Control inputs, display outputs, operating modes, and DCS-BIOS coverage must be checked for that module. These are investigation priorities, not compatibility claims or release commitments.

## Related radio projects

- [ARC-210 radio panel](https://github.com/dgdimick/ARC-210-DCS-Display) — my other radio panel project.
- [ARC-186 COMM-VHF radio panel](https://github.com/dgdimick/ARC-186-DCS-Display) — my planned VHF panel with its own Teensy 4.1 and USB connection.

## A central directory for SIMPIT builders

I’d love to see a central GitHub directory linking to projects from SIMPIT builders like me—a place to find panels, code, PCB designs, printable parts, and build guides for SIMPITs of every size. It could link back to each builder’s own repository so the files, updates, and credit stay with the original project. This is an idea I’d like to see happen, rather than a project I’ve committed to building myself.

If you know of one or would like to discuss it, let me know in [Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions).

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
