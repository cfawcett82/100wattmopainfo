At 80ns, the laser starts to act like a hammer. The pulses are long enough to hold significant heat, making this a prime setting for Deep Metal Engraving and Brass/Copper Ablation. Because copper and brass reflect so much light, the extra "push" of the 80ns pulse helps break the surface tension of the metal.
Your cutoff frequency is 375 kHz.
## Routine A: The Speed vs. Frequency Map (80ns)
Goal: Finding the "Material Removal" rate. You want to see how fast you can move while still clearing a significant amount of metal.
Library Baseline Setup:

   1. C00 Settings: Pulse: 80ns | Power: 80% (Static) | Interval: 0.04mm (Slightly wider for heat).
   2. Save to Library: MOPA 100W > Phase 3.5 > 80ns Speed-Freq Test.

Material Test Generator Config:

* X-Axis (Speed): 300 mm/s to 1500 mm/s | Count: 7.
* Y-Axis (Frequency): 375 kHz (Cutoff) to 4000 kHz (Max) | Count: 8.
* Calculated Steps: 375, 500, 1000, 1500, 2000, 2500, 3000, 4000 kHz.
* Observation: Notice the sound change. The 375 kHz row will have a much lower, more aggressive "growl" compared to the high-pitched "whine" of 4000 kHz.

------------------------------
## Routine B: The Power vs. Frequency Map (80ns)
Goal: Mapping "Brute Force." At 80ns, 100% power is very destructive. This test shows you if 100% power is usable or if it just creates a melted mess.
Library Baseline Setup:

   1. C00 Settings: Pulse: 80ns | Speed: [Winner from Routine A] | Interval: 0.04mm.
   2. Save to Library: MOPA 100W > Phase 3.5 > 80ns Power-Freq Test.

Material Test Generator Config:

* X-Axis (Power): 20% to 100% | Count: 9.
* Y-Axis (Frequency): 375 kHz to 4000 kHz | Count: 8.
* Observation: Look at the walls of the squares. If the walls are straight and clean, your frequency/power balance is good. If the walls look like they are "slumping" or melted, you need to either increase speed or increase frequency to spread the heat out.

------------------------------
## Summary Table for 80ns Tests

| Routine | Static Settings | Variable X (Steps) | Variable Y (Steps) |
|---|---|---|---|
| A (Speed) | 80ns, 80% Power | 300 - 1500 mm/s (7) | 375 - 4000 kHz (8) |
| B (Power) | 80ns, [Winner A] | 20% - 100% (9) | 375 - 4000 kHz (8) |

## Execution Tip: The "Heat Wall"
At 80ns, you will likely hit a "heat wall" on the lower frequency settings. If you find the metal is staying too hot and causing the engraving to look black and crusty, try adding a "Pass Delay" in your sub-layer settings, or run this test on a thicker piece of scrap that can act as a heat sink.
Ready for 100ns? This is the last pulse width before we jump into the "Phase 4: Heavy Punch" territory (150ns+). At 100ns, the cutoff frequency drops even further to 300 kHz.

