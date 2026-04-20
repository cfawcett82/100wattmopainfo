For the 20ns Q-Pulse, we move into the most versatile range of your MOPA. Since 20ns is the transition point from "surface coloring" to "black marking," we will run two distinct test routines to map out its behavior.
## Routine A: The Speed vs. Frequency Map
Goal: Find the cleanest black or dark mark by balancing the repetition rate against travel speed.
Library Baseline Setup:

   1. C00 Settings: Pulse: 20ns | Power: 40% (Static) | Interval: 0.02mm.
   2. Save to Library: MOPA 100W > Phase 2 > 20ns Speed-Freq Test.

Material Test Generator Config:

* X-Axis (Speed): 500 mm/s to 3000 mm/s | Count: 6 (500mm increments).
* Y-Axis (Frequency): 1500 kHz (Cutoff) to 4000 kHz (Max) | Count: 6.
* Calculated Steps: 1500, 2000, 2500, 3000, 3500, 4000 kHz.
* Result: This grid shows you if a high-speed "light" mark at 4000kHz is better than a medium-speed "heavy" mark at 1500kHz.

------------------------------
## Routine B: The Power vs. Frequency Map
Goal: Once you find your ideal speed from Routine A, find the power threshold that causes burning.
Library Baseline Setup:

   1. C00 Settings: Pulse: 20ns | Speed: [Your Winner from Routine A] (Static) | Interval: 0.02mm.
   2. Save to Library: MOPA 100W > Phase 2 > 20ns Power-Freq Test.

Material Test Generator Config:

* X-Axis (Power): 10% to 100% | Count: 10.
* Y-Axis (Frequency): 1500 kHz (Cutoff) to 4000 kHz (Max) | Count: 6.
* Static Speed: Use the best result from Routine A.
* Result: This reveals the "burn point." You will likely see that at 1500kHz, the metal starts to glow/melt at 70% power, while at 4000kHz, it may stay clean all the way to 100%.

------------------------------
## Summary Table for 20ns Tests

| Routine | Static Settings | Variable X | Variable Y |
|---|---|---|---|
| A (Speed) | 20ns, 40% Power | 500 - 3000 mm/s | 1500 - 4000 kHz |
| B (Power) | 20ns, [Best Speed] | 10% - 100% | 1500 - 4000 kHz |

## Execution Tip: The 20ns "Sweet Spot"
When looking at your results, pay close attention to the 1500–2000 kHz range. This is where the 20ns pulse has its highest peak power. If you are marking Anodized Aluminum, this range usually produces the richest, matte black. If you go up to 4000 kHz, the mark will likely shift toward a "dark gray" because the energy per pulse is too low to fully carbonize the surface.
