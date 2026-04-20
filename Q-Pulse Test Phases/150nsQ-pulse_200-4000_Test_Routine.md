At 150ns, you are moving into the "High Energy" domain. Your cutoff frequency is now 200 kHz.
At this pulse width, the MOPA starts behaving like a mini-jackhammer. This is excellent for deep metal removal, but it generates significant heat. You will notice that as the frequency goes up, the "punch" drops off very quickly compared to shorter pulses.
## Routine A: The Speed vs. Frequency Map (150ns)
Goal: Find the "Depth vs. Slag" balance. You want to see how fast you can clear material without leaving melted edges.
Library Baseline Setup:

   1. C00 Settings: Pulse: 150ns | Power: 80% (Static) | Interval: 0.05mm.
   2. Save to Library: MOPA 100W > Phase 4 > 150ns Speed-Freq Test.

Material Test Generator Config:

* X-Axis (Speed): 100 mm/s to 1000 mm/s | Count: 10.
* Y-Axis (Frequency): 200 kHz (Cutoff) to 2000 kHz (Max) | Count: 7.
* Calculated Steps: 200, 400, 600, 800, 1000, 1500, 2000 kHz.
   * Note: The JPT M7 usually caps 150ns at 2000kHz; check your laser passport.
* Observation: The 200-400 kHz range will be your "Removal" zone. Anything above 1000 kHz will likely look very weak at this long pulse duration.

------------------------------
## Routine B: The Power vs. Frequency Map (150ns)
Goal: Stress test the 100W at low frequency. This will show you the maximum "bite" the laser can take out of the metal.
Library Baseline Setup:

   1. C00 Settings: Pulse: 150ns | Speed: [Winner from Routine A] | Interval: 0.05mm.
   2. Save to Library: MOPA 100W > Phase 4 > 150ns Power-Freq Test.

Material Test Generator Config:

* X-Axis (Power): 20% to 100% | Count: 9.
* Y-Axis (Frequency): 200 kHz to 2000 kHz | Count: 7.
* Observation: Watch for re-melting. If the bottom of the square looks like cooled lava, you are dumping too much heat. You need to either increase the speed or increase the line interval to 0.06mm.

------------------------------
## Summary Table for 150ns Tests

| Routine | Static Settings | Variable X (Steps) | Variable Y (Steps) |
|---|---|---|---|
| A (Speed) | 150ns, 80% Power | 100 - 1000 mm/s (10) | 200 - 2000 kHz (7) |
| B (Power) | 150ns, [Winner A] | 20% - 100% (9) | 200 - 2000 kHz (7) |

## The "150ns Debris" Warning
At 150ns, the material removal is aggressive enough that the dust produced is actually metallic particles. This dust is conductive and abrasive.

   1. Clean your lens immediately after this test.
   2. Use a strong vacuum or air assist to keep that dust from settling back into the engrave, as it will "shield" the metal from the next pulse.

