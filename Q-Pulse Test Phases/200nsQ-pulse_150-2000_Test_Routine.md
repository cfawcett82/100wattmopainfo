At 200ns, you are hitting the "Maximum Punch" territory. This pulse width is the standard for heavy-duty metal removal. Because the pulse is so long, the laser dumps a massive amount of energy into the spot, creating a violent vaporization.
Your cutoff frequency is 150 kHz, and the maximum frequency for this duration is typically capped at 2000 kHz (2 MHz).
## Routine A: The Speed vs. Frequency Map (200ns)
Goal: Finding the "Deep Dig" sweet spot. You are looking for the speed that maximizes depth without letting the metal liquefy and "slump."
Library Baseline Setup:

   1. C00 Settings: Pulse: 200ns | Power: 80% (Static) | Interval: 0.06mm.
   2. Save to Library: MOPA 100W > Phase 4 > 200ns Speed-Freq Test.

Material Test Generator Config:

* X-Axis (Speed): 100 mm/s to 1000 mm/s | Count: 10.
* Y-Axis (Frequency): 150 kHz (Cutoff) to 2000 kHz (Max) | Count: 6.
* Calculated Steps: 150, 300, 500, 1000, 1500, 2000 kHz.
* Observation: The 150–300 kHz range will sound like a small hammer drill. This is your primary zone for 3D engraving and coin making.

------------------------------
## Routine B: The Power vs. Frequency Map (200ns)
Goal: Mapping the heat threshold. 100W at 200ns/150kHz is intense. This test will reveal if you can actually use 100% power without warping the workpiece.
Library Baseline Setup:

   1. C00 Settings: Pulse: 200ns | Speed: [Winner from Routine A] | Interval: 0.06mm.
   2. Save to Library: MOPA 100W > Phase 4 > 200ns Power-Freq Test.

Material Test Generator Config:

* X-Axis (Power): 20% to 100% | Count: 9.
* Y-Axis (Frequency): 150 kHz to 2000 kHz | Count: 6.
* Observation: Check for "Mushrooming" at the edges. If the metal at the border of the square is raised above the surface of the plate, you are dumping too much heat. You’ll need a "Cleanup Pass" from Phase 1 or 2 to shave those lips off.

------------------------------
## Summary Table for 200ns Tests

| Routine | Static Settings | Variable X (Steps) | Variable Y (Steps) |
|---|---|---|---|
| A (Speed) | 200ns, 80% Power | 100 - 1000 mm/s (10) | 150 - 2000 kHz (6) |
| B (Power) | 200ns, [Winner A] | 20% - 100% (9) | 150 - 2000 kHz (6) |

## The "Z-Step" Consideration
Because 200ns is designed to go deep, the laser will eventually move out of focus as it carves away material.

* If your test squares look great for the first few passes but then start to get "fuzzy" or stop digging, you have reached the limit of your Depth of Field.
* For your final project, you will want to enable Z-Step in the layer settings (e.g., -0.05mm per pass) to keep the "hammer" at the bottom of the hole.
