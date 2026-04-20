At 45ns, you have reached the bridge between "Marking" and "Engraving." Your cutoff frequency has dropped to ~660 kHz.
At this pulse width, you can still achieve dark surface marks, but you’ll notice the laser is starting to "bite" into the material. The goal here is to find the balance where the laser removes material smoothly without creating excessive slag (melted lips around the engrave).
## Routine A: The Speed vs. Frequency Map (45ns)
Goal: Find the "Clean Removal" zone. You want the speed that allows vaporization without overheating the surrounding metal.
Library Baseline Setup:

   1. C00 Settings: Pulse: 45ns | Power: 60% (Static) | Interval: 0.03mm.
   2. Save to Library: MOPA 100W > Phase 3 > 45ns Speed-Freq Test.

Material Test Generator Config:

* X-Axis (Speed): 500 mm/s to 2000 mm/s | Count: 7.
* Y-Axis (Frequency): 660 kHz (Cutoff) to 4000 kHz (Max) | Count: 6.
* Calculated Steps: 660, 1000, 1500, 2000, 3000, 4000 kHz.
* Observation: The lower frequencies (660–1000 kHz) will dig deeper. The higher frequencies (3000–4000 kHz) will act more like a "polishing" pass.

------------------------------
## Routine B: The Power vs. Frequency Map (45ns)
Goal: Identify the "Efficiency Threshold." Since you have 100W, you want to see if 100% power at a higher frequency is cleaner than 50% power at the cutoff frequency.
Library Baseline Setup:

   1. C00 Settings: Pulse: 45ns | Speed: [Winner from Routine A] | Interval: 0.03mm.
   2. Save to Library: MOPA 100W > Phase 3 > 45ns Power-Freq Test.

Material Test Generator Config:

* X-Axis (Power): 20% to 100% | Count: 9.
* Y-Axis (Frequency): 660 kHz to 4000 kHz | Count: 6.
* Observation: Look for "Sooting." If the square is covered in heavy black powder that doesn't wipe off easily, you are likely too high on power and too low on frequency for that speed.

------------------------------
## Summary Table for 45ns Tests

| Routine | Static Settings | Variable X (Steps) | Variable Y (Steps) |
|---|---|---|---|
| A (Speed) | 45ns, 60% Power | 500 - 2000 mm/s (7) | 660 - 4000 kHz (6) |
| B (Power) | 45ns, [Winner A] | 20% - 100% (9) | 660 - 4000 kHz (6) |

## The "Step-Over" Tip for 45ns
As pulses get longer, the "spot size" effectively feels larger due to the heat spread. If your results look "furry" or rough, try increasing your Line Interval slightly (e.g., from 0.03mm to 0.04mm). This gives the material a micro-second to cool between lines, often resulting in a much cleaner, flatter bottom.
