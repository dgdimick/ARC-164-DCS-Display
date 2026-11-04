# ARC-164 PCBs

**Last updated: November 4, 2026 at 2:43 AM MST (America/Denver)**

I’m developing the current PCB designs. No PCB design files are currently published.

## Control layout

I’m using **rotary encoders for all five frequency controls**, with rotary switches for MAIN and PRESET and encoders for VOL and channel. I’ve restored my original encoder project locally and still need to check the layout, clearances, wiring, and test fit before publishing the updated boards.

**I’m keeping rotary encoders for all five frequency controls, including future ARC-164 versions.** Fitting frequency rotary switches would require enlarging the holes and cutting anti-rotation alignment slots in the clear underpanel, so I won’t offer a frequency rotary-switch version. See the [current frequency-control plan](../README.md#frequency-controls).

## Display boards

I’m using **Kingbright SC36-11SURKWA** red, 0.36-inch, common-cathode LED digits: **six for frequency and two for preset**. I’ll order **10, including two spares**, from [Mouser, part 604-SC36-11SURKWA](https://www.mouser.com/en/ProductDetail/Kingbright/SC36-11SURKWA?qs=FRBiz4Wv1YMkVf5BvlPtDA%3D%3D). The display PCB design must use this part’s footprint and pinout, including common cathodes on pins 1 and 6. Spacing, mounting height, visibility through the smoked covers, and physical fit still need checking. See the [current display plan](../README.md#seven-segment-display-plan) and [order sheet](../README.md#order-sheet--rotary-controls-and-led-digits).
