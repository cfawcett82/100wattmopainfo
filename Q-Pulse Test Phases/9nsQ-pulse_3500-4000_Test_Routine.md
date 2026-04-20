For these tests, we shift the strategy. Instead of varying Power, we lock Power and Q-Pulse as statics and use the grid to find the "sweet spot" between Speed and Frequency.
Since the 13ns pulse has a significant range between its cutoff and its maximum, this test will reveal exactly how the laser's "character" changes as you trade pulse energy for repetition rate.
## Test Routine: 9ns Q-Pulse (High Frequency/Low Energy)
Goal: Finding the transition from surface marking to clean ablation.
Library Baseline Setup:

   1. C00 Settings: Pulse: 9ns | Power: 30% (Static) | Interval: 0.01mm.
   2. Save to Library: "MOPA 100W > Phase 1.5 > 9ns Freq-Speed Test".

Material Test Generator Config:

* X-Axis (Speed): 100 mm/s to 1000 mm/s | Count: 10 (100mm increments).
* Y-Axis (Frequency): 3500 kHz to 4000 kHz | Count: 3.
* Note: This creates three rows
   * 3500kHz - Cutoff
   * 3750kHz
   * 4000kHz - Max
* Static Power: 30%.

------------------------------
## Test Routine: 13ns Q-Pulse (The "Range" Test)
Goal: Testing the full range of the 13ns pulse from its 100W "Punch" to its 4MHz "Hum".
Library Baseline Setup:

   1. C00 Settings: Pulse: 13ns | Power: 40% (Static) | Interval: 0.01mm.
   2. Save to Library: "MOPA 100W > Phase 1.5 > 13ns Freq-Speed Test".

Material Test Generator Config:

* X-Axis (Speed): 100 mm/s to 1000 mm/s | Count: 10 (100mm increments).
* Y-Axis (Frequency): 2500 kHz to 4000 kHz | Count: 7.
* Calculated Steps: 2500, 2750, 3000, 3250, 3500, 3750, 4000 kHz.
* Static Power: 40%.

------------------------------
## Why this Frequency Test is important
In this 13ns test, as the Frequency moves from 2500 kHz (Cutoff) up to 4000 kHz:

   1. The Average Power stays the same (100W).
   2. The Pulse Energy drops because the 100 Watts are being spread across more pulses per second.
   3. Visual Result: The 2500 kHz row will likely look "hotter" and rougher, while the 4000 kHz row will look smoother and more polished, despite the Power setting being identical.

## Directions for Execution

   1. Assign the 9ns or 13ns baseline from your library to the Material Test "Edit Material Settings."
   2. Verify the Frequency range matches the table above in the Axis parameters.
   3. Ensure Enable Text is on so you can see which row is which Frequency.
   4. Observation: Look for the square where the mark is darkest but the metal hasn't started to "warp" or "glow" excessively.
