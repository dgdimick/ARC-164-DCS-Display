# ARC-164 Radio Panel for DCS

<p align="center">
  <img src="images/ARC-164_uhf_panel.jpg" width="500" alt="ARC-164 UHF radio panel reference photo">
</p>

*Panel reference photo: PC Flights.*

## My next project

Once I have completed the [ARC-210 radio panel](https://github.com/dgdimick/ARC-210-DCS-Display), the **AN/ARC-164 UHF radio panel** will be my next project.

The plan is to build a physical ARC-164 panel for my DCS A-10C II cockpit, with working controls and a display linked to DCS through DCS-BIOS.

This repository is a placeholder for now. I am exploring display options and the panel layout, but the ARC-210 remains my priority. There is no firmware or finished hardware design available here yet, and I have not set a release date.

As development progresses, I will add build notes, hardware details, firmware, and photos here.

## Exploring a shared controller for both radios

I am looking into using the Teensy inside the ARC-164 to also run a separate [COMM-VHF radio panel](https://pcflights.com/a-10c-thunderbolt-warthog-comm-vhf-panel/). The idea is to connect the VHF panel to the ARC-164 with a plug-in cable, with the ARC-164's Teensy handling both panels through DCS-BIOS.

My aim is to make completing your radios more affordable by sharing one controller and USB connection. This is still being investigated: the wiring, connector, display drivers, and combined input/output requirements have not been finalized, and any cost savings remain to be confirmed.

I also plan to offer a **standalone VHF version with its own controller and USB connection**, so you can build the VHF radio without having to build the ARC-164.

Both options are proposed designs, not available hardware or firmware yet. I will document the supported arrangements and parts as development progresses.

## PC Flights affiliation

I am not affiliated with PC Flights in any way. I simply chose to use their panels for my own cockpit projects.
