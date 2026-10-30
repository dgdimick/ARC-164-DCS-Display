# ARC-164 Radio Panel for DCS

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

## Encoder PCB plan

The ARC-164 will need a **new encoder PCB**, because its frequency-encoder positions do not line up with the ARC-210 encoder PCB. The plan is to mount **all five frequency encoders and the preset-channel encoder on one PCB**, assuming there is enough room and clearance behind the faceplate. The final board outline and encoder placement will be confirmed during the mechanical layout.

## Exploring a shared controller for both radios

I am looking into using the Teensy inside the ARC-164 to also run a separate [COMM-VHF radio panel](https://pcflights.com/a-10c-thunderbolt-warthog-comm-vhf-panel/). The idea is to connect the VHF panel to the ARC-164 with a plug-in cable, with the ARC-164's Teensy handling both panels through DCS-BIOS.

My aim is to make completing your radios more affordable by sharing one controller and USB connection. This is still being investigated: the wiring, connector, display drivers, and combined input/output requirements have not been finalized, and any cost savings remain to be confirmed.

I also plan to offer a **standalone VHF version with its own controller and USB connection**, so you can build the VHF radio without having to build the ARC-164.

Both options are proposed designs, not available hardware or firmware yet. I will document the supported arrangements and parts as development progresses.

## Related radio project

Follow the [ARC-186 COMM-VHF radio panel project](https://github.com/dgdimick/ARC-186-DCS-Display) for its build plans, including the proposed shared ARC-164 controller and standalone options.

## Questions and community builds

Visit [GitHub Discussions](https://github.com/dgdimick/ARC-164-DCS-Display/discussions) to ask questions, share ideas, and post photos of your build. Whether you’re planning your panel or already working on it, you’re welcome to join in!

## PC Flights affiliation

I am not affiliated with [PC Flights](https://pcflights.com/) in any way. I simply chose to use their panels for my own cockpit projects.
