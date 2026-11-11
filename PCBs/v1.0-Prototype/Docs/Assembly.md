# ARC-164 Version 1.0 prototype assembly

**Last updated: November 10, 2026 at 5:45 PM MST (America/Denver)**

**LED Sub Board v1.2 is now published for Main Board v1.2.** I printed the latest mockup at **100%** and it passed the fit test, including **frequency and channel LED alignment and J20 connector/cable clearance**. The final layout keeps the **FREQ LEDs up 0.5 mm**, the **channel LEDs up 0.5 mm with their earlier 0.5 mm leftward adjustment**, and **J20 up 2 mm total** from the previous mounting position. The **0.75 mm gaps, 6 mm display bodies and tested 8 mm mounting stack** remain unchanged. **Use Main Board v1.2 with LED Sub Board v1.2; older Sub Boards do not match this Main Board. Assembled electrical testing is still pending.**


I’ll post pictures of my build to help you follow the assembly steps.

**General assembly tip:** It’s usually best to solder the shortest components first, then work up to the taller parts. This makes it easier to keep components seated against the PCB while soldering. Follow the board-specific order below.

### Main Board

1. **Solder the resistors first.** Install the resistors on the **back of the Main Board** and solder them before fitting the front-side components.
2. **Solder the pin connector on the back of the PCB.** Fit and solder the **J10 control-cable pin header on the back of the Main Board** before starting any soldering of components mounted on the front.
3. **Solder the backlight LEDs next.** Install the LEDs on the **front of the Main Board**, facing the panel. Check each LED’s orientation before soldering: match its **anode (+) and cathode (−)** to the PCB markings. For new, untrimmed LEDs, the longer lead is the anode; the shorter lead and flat side of the body identify the cathode. On the current footprint, **pad 1 is the cathode** and **pad 2 is the anode**.

4. **Wire the switches.** For the wired TONE, SQL, LOAD, TEST DISPLAY, and STATUS switches, solder a **6-inch (approximately 15 cm) wire to each required switch contact** first. Before soldering, you may want to feed the wires through the corresponding switch holes to make routing easier. Then flip the Main Board over and solder the free ends into the matching **labeled switch solder pads**, checking the signal and GND connections. It is fine to make these switch-wire connections on the **back of the Main Board**.

### Panel-to-Main-Board mounting

I currently have **13.5 mm between the panel and Main Board**. I may use **14 mm** to let the LEDs sit slightly farther back from the glass. I’ll check the spacing when the manufactured PCBs arrive and add an extra spacer if needed. Check the complete mounting stack, control alignment, and clearances before tightening the hardware.

### LED Sub-Board mounting

**The earlier Sub Board mockup passed my 100% print and LED alignment test behind the faceplate**, including the **0.75 mm LED gaps**, **6 mm display bodies**, and **8 mm mounting stack**. In that earlier tested adjustment, I moved the **channel LEDs 1 mm right** and the **FREQ LEDs 0.5 mm left** from the previous test layout. Each of the four mounts uses a **20 mm screw, a 6 mm-thick nut and two 1 mm washers**. **Assembled electrical testing remains to be done.** **November 10 follow-up:** The latest **Sub Board v1.2** mockup has now passed the **100% print, frequency/channel LED alignment and J20 connector/cable-clearance fit checks with Main Board v1.2**, and its files and tested STL are published. Assembled electrical testing remains pending.

The **LED Sub-Board mounts above the Main Board**, toward the panel. Its mounting hardware connects the **bottom of the Sub-Board to the top of the Main Board**. I use **four Sub-Board mounts**, each with a **20 mm screw, a 6 mm-thick nut, and two 1 mm-thick washers**, giving **8 mm spacing** between the Main Board and LED Sub-Board. Check display alignment behind both windows and clearance around the components before tightening the hardware.

### LED Sub-Board

**Use Main Board v1.2 with the matching LED Sub Board v1.2.** The latest Sub Board mockup passed my **100% print and fit test on November 10, 2026**, including LED alignment and J20 connector/cable clearance. Older Sub Boards do not match Main Board v1.2. Assembled electrical testing remains pending.

1. **Solder the LED displays first.** Fit the displays on the **front of the Sub-Board**. Before soldering, check each display’s orientation and pin 1 against the PCB markings, and make sure the decimal points are in the correct position. Keep the displays seated evenly while soldering.
2. **Solder the pin connector on the back.** After fitting the displays, install and solder the **J20 display-cable pin header on the back of the Sub-Board**, matching pin 1 to the PCB markings.


## Power Driver Board

Fit low components first. Solder empty 24-pin sockets for U11/U12 and the empty 14-pin socket for U13 before inserting ICs. Match IC pin 1 and socket notches to the board. Fit two 24-pin female sockets to the Power Driver Board and matching male headers to the Teensy’s outer rows; omit separate male headers if already fitted. The Teensy can then be unplugged. Check clearance above sockets before choosing Power Driver Board standoffs.

### Power Driver Board mounting

I mount the **Power Driver Board below the Main Board using 10 standoffs, with its components facing down**, away from the Main Board. **Each standoff must be longer than 20 mm**; the exact length can vary to provide clearance for components, IC sockets, Teensy headers, and cables. Check the full stack before tightening the hardware.

Review [Wiring.md](Wiring.md), pin-1 cable orientation and the physical stack clearances before powering.
