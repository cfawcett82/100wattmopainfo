For the 30ns Q-Pulse, we are entering the territory of "Heavy Marking." This is often the preferred pulse width for deep, dark blacks on stainless steel and high-speed marks on brass or copper.
At 30ns, your cutoff frequency is 1000 kHz. Testing from 1000 kHz up to 4000 kHz will show you the transition from a high-energy "impact" pulse to a high-frequency "polishing" pulse.
## Routine A: The Speed vs. Frequency Map (30ns)
Goal: Determine the maximum production speed for a dark, consistent mark.
Library Baseline Setup:

   1. C00 Settings: Pulse: 30ns | Power: 50% (Static) | Interval: 0.02mm.
   2. Save to Library: MOPA 100W > Phase 2 > 30ns Speed-Freq Test.

Material Test Generator Config:

* X-Axis (Speed): 500 mm/s to 3500 mm/s | Count: 7 (500mm increments).
* Y-Axis (Frequency): 1000 kHz (Cutoff) to 4000 kHz (Max) | Count: 7.
* Calculated Steps: 1000, 1500, 2000, 2500, 3000, 3500, 4000 kHz.
* Observation: At 1000 kHz, you might see more "spatter" or a rougher texture. At 4000 kHz, the mark will be smoother but potentially lighter.

------------------------------
## Routine B: The Power vs. Frequency Map (30ns)
Goal: Find the "Over-Power" limit where the material starts to warp or discolor from heat soak.
Library Baseline Setup:

   1. C00 Settings: Pulse: 30ns | Speed: [Best Speed from Routine A] | Interval: 0.02mm.
   2. Save to Library: MOPA 100W > Phase 2 > 30ns Power-Freq Test.

Material Test Generator Config:

* X-Axis (Power): 20% to 100% | Count: 9 (10% increments).
* Y-Axis (Frequency): 1000 kHz to 4000 kHz | Count: 7.
* Observation: This test is critical for 100W users. 100W at 30ns/1000kHz is a massive amount of heat. Look for where the metal begins to "bow" or where the black mark turns into a charred gray—that is your upper limit.

------------------------------
## Summary Table for 30ns Tests

| Routine | Static Settings | Variable X (Steps) | Variable Y (Steps) |
|---|---|---|---|
| A (Speed) | 30ns, 50% Power | 500 - 3500 mm/s (7) | 1000 - 4000 kHz (7) |
| B (Power) | 30ns, [Winner A] | 20% - 100% (9) | 1000 - 4000 kHz (7) |

## Comparison: 20ns vs 30ns
When you compare these 30ns cards to your 20ns cards, you will notice:

   1. The 30ns 1000kHz row will be significantly more aggressive than anything on the 20ns card.
   2. Overlap: The "Speed" sweet spot will likely shift higher because the 30ns pulse carries more energy, allowing you to move faster while still achieving a dark mark.
