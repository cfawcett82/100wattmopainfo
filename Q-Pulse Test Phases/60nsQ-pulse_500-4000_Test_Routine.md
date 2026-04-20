At 60ns, you are in the "Workhorse" pulse width for MOPA fiber lasers. This is the pulse width most people use to replicate the behavior of a standard Q-switched (non-MOPA) laser, but with the added benefit of being able to crank the frequency up for a smoother finish.
Your cutoff frequency is 500 kHz.
## Routine A: The Speed vs. Frequency Map (60ns)
Goal: Find the "Clean Floor" balance. You are looking for the combination that vaporizes metal without leaving "melted slag" or deep ridges.
Library Baseline Setup:

   1. C00 Settings: Pulse: 60ns | Power: 70% (Static) | Interval: 0.03mm.
   2. Save to Library: MOPA 100W > Phase 3 > 60ns Speed-Freq Test.

Material Test Generator Config:

* X-Axis (Speed): 400 mm/s to 1800 mm/s | Count: 8 (200mm increments).
* Y-Axis (Frequency): 500 kHz (Cutoff) to 4000 kHz (Max) | Count: 8.
* Calculated Steps: 500, 1000, 1500, 2000, 2500, 3000, 3500, 4000 kHz.
* Observation: The 500 kHz row will be your deepest and most aggressive. The 4000 kHz row will likely be very shallow and act as a "satin" finish.

------------------------------
## Routine B: The Power vs. Frequency Map (60ns)
Goal: Mapping the 100W potential. At 60ns, you have enough energy to really dig. This test finds where the heat becomes uncontrollable.
Library Baseline Setup:

   1. C00 Settings: Pulse: 60ns | Speed: [Winner from Routine A] | Interval: 0.03mm.
   2. Save to Library: MOPA 100W > Phase 3 > 60ns Power-Freq Test.

Material Test Generator Config:

* X-Axis (Power): 20% to 100% | Count: 9 (10% increments).
* Y-Axis (Frequency): 500 kHz to 4000 kHz | Count: 8.
* Observation: If you see the edges of the squares starting to "curl" or lift (especially on thinner metal), you have exceeded the thermal capacity of the material at that frequency.

------------------------------
## Summary Table for 60ns Tests

| Routine | Static Settings | Variable X (Steps) | Variable Y (Steps) |
|---|---|---|---|
| A (Speed) | 60ns, 70% Power | 400 - 1800 mm/s (8) | 500 - 4000 kHz (8) |
| B (Power) | 60ns, [Winner A] | 20% - 100% (9) | 500 - 4000 kHz (8) |

## The "60ns Finish" Secret
If your goal is Deep Engraving, the 500 kHz row is your tool for depth. However, once you reach your desired depth, running a final pass using the settings from the 3000–4000 kHz row (at low power) will "polish" the bottom of the engraving, turning it from a dark, rough texture to a clean, bright finish.
Shall we move to 80ns and 100ns? We are entering the "Rapid Ablation" zone where frequency ranges start to compress significantly as the cutoff frequency continues to drop.

