# ARC-164 Radio Panel for DCS

**Last updated: October 30, 2026 at 3:42 AM MDT (America/Denver)**
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

Once I have completed the [ARC-210 radio panel](https://github.com/dgdimick/ARC-210-DCS-Display), the **AN/ARC-164 UHF radio panel** will be my next project.

The plan is to build a physical ARC-164 panel for my DCS A-10C II cockpit, with working controls and a display linked to DCS through DCS-BIOS.

This repository is a placeholder for now. I am exploring display options and the panel layout, but the ARC-210 remains my priority. There is no firmware or finished hardware design available here yet, and I have not set a release date.

As development progresses, I will add build notes, hardware details, firmware, and photos here.

## Controller choice — Teensy 4.1

I’m staying with the **Teensy 4.1** for the ARC-164. Its compact size makes it easier to fit behind the faceplate, it offers 42 readily accessible I/O pins, and it keeps the controller consistent with the ARC-210 project. The final ARC-164 pin allocation still needs to be verified.

The **Teensy 4.1 runs at 600 MHz**, compared with **16 MHz for the classic Arduino Uno R3, Mega 2560, and ATmega328P Nano** — **37.5 times the CPU clock frequency**. This provides processing headroom for display updates and controls; it is not a measured 37.5-times improvement in display refresh speed. See the [Teensy specifications](https://www.pjrc.com/store/teensy41.html) and [classic Arduino board comparison](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/Why-Teensy.md).

I considered the Arduino Due, but it is physically larger and would not save money at the prices checked on **October 30, 2026**: a genuine Due with headers was listed at **$49.40** at [DigiKey](https://www.digikey.com/en/products/detail/arduino/A000062/3712582), compared with **$31.50** for a Teensy 4.1 or **$35.95** with headers at [SparkFun](https://www.sparkfun.com/development-boards/microcontrollers/teensy/teensy-boards.html), before shipping and tax. These are reference prices, not fixed build costs.

Ethernet is not required for the planned USB DCS-BIOS connection. The Teensy 4.1 version without Ethernet is also an option; its listed price was **$29.60** at the same price check. Teensy 4.1 uses **3.3 V logic**, and its inputs are not 5 V tolerant, so display-driver connections must be designed accordingly. See the [PJRC specifications](https://www.pjrc.com/store/teensy41.html).

## Why I keep using Teensy 4.1s

I’m using a Teensy 4.1 in each radio to keep the controller hardware and programming workflow consistent across the ARC-210, ARC-164, and ARC-186 projects. Each panel gets its own controller and USB connection, so it can be built and operated independently. Pin assignments and firmware will still be specific to each radio.

The Teensy 4.1 offers 42 readily accessible I/O pins and a 600 MHz processor, leaving room for controls, display updates, and future additions. Classic Arduino Uno and Mega boards run at 16 MHz. See [why I chose the Teensy 4.1](https://github.com/dgdimick/ARC-210-DCS-Display/blob/master/Docs/Why-Teensy.md) for the detailed comparison; clock speed alone does not determine display refresh performance.

I considered a classic Arduino Nano for the ARC-186, but the genuine Nano was listed at **$25.70** versus **$29.60** for the Teensy 4.1 without Ethernet—a difference of only **$3.90**, before shipping and tax, at the October 30, 2026 price check. For that small difference, I prefer the Teensy’s faster processor, extra capacity, and consistency across the radio projects. Its **600 MHz** CPU provides more processing headroom for display updates and controls than the classic Nano’s **16 MHz** CPU. The [ARC-186 controller comparison](https://github.com/dgdimick/ARC-186-DCS-Display#controller-cost-comparison) lists the options and supplier links. Ethernet is not needed for the planned USB DCS-BIOS connections.

## Encoder PCB plan

The ARC-164 will need a **new encoder PCB**, because its frequency-encoder positions do not line up with the ARC-210 encoder PCB. The plan is to mount **all five frequency encoders and the preset-channel encoder on one PCB**, assuming there is enough room and clearance behind the faceplate. The final board outline and encoder placement will be confirmed during the mechanical layout.

## Separate controllers for each radio

The **ARC-164 and ARC-186 will each use their own Teensy 4.1**, with a separate USB connection to DCS-BIOS for each panel. Either radio can be built and operated independently. Dedicated controllers keep each panel's wiring and firmware separate and leave room for future additions.

The ARC-164 controller will operate the ARC-164 only; the [ARC-186 COMM-VHF panel](https://github.com/dgdimick/ARC-186-DCS-Display) will have its own controller. Hardware, pin assignments, and firmware remain under development.

## Related radio project

Follow the [ARC-186 COMM-VHF radio panel project](https://github.com/dgdimick/ARC-186-DCS-Display) for its build plans using a dedicated Teensy 4.1 and its own USB connection.

## Questions and community builds

Visit [GitHub Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions) to ask questions, share ideas, and post photos of your build. Whether you’re planning your panel or already working on it, you’re welcome to join in!

## PC Flights affiliation

I am not affiliated with [PC Flights](https://pcflights.com/) in any way. I simply chose to use their panels for my own cockpit projects.
