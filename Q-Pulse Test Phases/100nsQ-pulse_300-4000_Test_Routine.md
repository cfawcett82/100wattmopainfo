At 100ns, the laser transitions from "engraving" to "ablation." The energy per pulse is now high enough to physically eject material. This is the go-to setting for deep coin engraving or clearing large amounts of metal quickly.
Your cutoff frequency is 300 kHz.
## Routine A: The Speed vs. Frequency Map (100ns)
Goal: Find the "Vaporization Balance." You want the speed that removes the most material per pass without leaving behind a "re-melted" surface.
Library Baseline Setup:

   1. C00 Settings: Pulse: 100ns | Power: 80% (Static) | Interval: 0.05 mm (Widened to prevent slag buildup).
   2. Save to Library: MOPA 100W > Phase 3.5 > 100ns Speed-Freq Test.

Material Test Generator Config:

* X-Axis (Speed): 200 mm/s to 1200 mm/s | Count: 6 (200mm increments).
* Y-Axis (Frequency): 300 kHz (Cutoff) to 4000 kHz (Max) | Count: 8.
* Steps: 300, 500, 1000, 1500, 2000, 2500, 3000, 4000 kHz.
* Observation: The 300–500 kHz range will be noticeably louder and more aggressive. The 4000 kHz row will likely feel "thin," as the energy per pulse is very low at this duration/frequency combo.

------------------------------
## Routine B: The Power vs. Frequency Map (100ns)
Goal: Stress test the 100W output. You need to see if 100% power at the cutoff frequency (300 kHz) causes the metal to bubble or if it carves cleanly.
Library Baseline Setup:

   1. C00 Settings: Pulse: 100ns | Speed: [Winner from Routine A] | Interval: 0.05 mm.
   2. Save to Library: MOPA 100W > Phase 3.5 > 100ns Power-Freq Test.

Material Test Generator Config:

* X-Axis (Power): 20% to 100% | Count: 9.
* Y-Axis (Frequency): 300 kHz to 4000 kHz | Count: 8.
* Observation: Pay attention to the bottom texture. At high power and low frequency, you may see "peaks and valleys." If the floor is too rough, you need to increase your Frequency or your Line Interval.

------------------------------
## Summary Table for 100ns Tests

| Routine | Static Settings | Variable X (Steps) | Variable Y (Steps) |
|---|---|---|---|
| A (Speed) | 100ns, 80% Power | 200 - 1200 mm/s (6) | 300 - 4000 kHz (8) |
| B (Power) | 100ns, [Winner A] | 20% - 100% (9) | 300 - 4000 kHz (8) |

## The "100W Deep Dig" Tip
If you are doing 3D Engraving (multiple passes), the 300 kHz row is your best friend. However, the debris (soot) created at 100ns is heavy. Ensure you have strong air assist pointed directly at the point of impact to blow the dust away, or the laser will spend its energy hitting the dust instead of the metal.

