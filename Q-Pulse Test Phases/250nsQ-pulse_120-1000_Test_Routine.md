At 250ns, your MOPA laser is optimized for maximum thermal shock. This setting is often used for cutting thin metal sheets or aggressively clearing material on metals that dissipate heat quickly (like Aluminum or Copper).
Your cutoff frequency is 120 kHz, and the maximum frequency typically drops to 1000 kHz (1 MHz). At this duration, anything above 500 kHz will feel significantly underpowered.
## Routine A: The Speed vs. Frequency Map (250ns)
Goal: Find the "Vaporization Peak." You want the frequency that provides the most depth before the metal begins to liquefy rather than vaporize.
Library Baseline Setup:

   1. C00 Settings: Pulse: 250ns | Power: 80% (Static) | Interval: 0.07mm (Wide step-over to manage heat).
   2. Save to Library: MOPA 100W > Phase 4 > 250ns Speed-Freq Test.

Material Test Generator Config:

* X-Axis (Speed): 50 mm/s to 800 mm/s | Count: 8.
* Y-Axis (Frequency): 120 kHz (Cutoff) to 1000 kHz (Max) | Count: 6.
* Calculated Steps: 120, 250, 400, 600, 800, 1000 kHz.
* Observation: The 120–250 kHz range will be extremely violent. You may see sparks or "starbursts" of molten metal. This is the "Ablation Zone."

------------------------------
## Routine B: The Power vs. Frequency Map (250ns)
Goal: Stress test the material's thermal limit. At 250ns, 100% power can easily warp a 1mm stainless plate.
Library Baseline Setup:

   1. C00 Settings: Pulse: 250ns | Speed: [Winner from Routine A] | Interval: 0.07mm.
   2. Save to Library: MOPA 100W > Phase 4 > 250ns Power-Freq Test.

Material Test Generator Config:

* X-Axis (Power): 20% to 100% | Count: 9.
* Y-Axis (Frequency): 120 kHz to 1000 kHz | Count: 6.
* Observation: Check for Slag (Dross). If the edges of the engrave are covered in beads of metal, you are dumping too much heat. Either increase your speed or increase your line interval.

------------------------------
## Summary Table for 250ns Tests

| Routine | Static Settings | Variable X (Steps) | Variable Y (Steps) |
|---|---|---|---|
| A (Speed) | 250ns, 80% Power | 50 - 800 mm/s (8) | 120 - 1000 kHz (6) |
| B (Power) | 250ns, [Winner A] | 20% - 100% (9) | 120 - 1000 kHz (6) |

## The "250ns Clean-Up" Strategy
Because 250ns creates a very rough, "toothy" surface, it is excellent for bonding applications (making metal stick to epoxy). If you want it to look pretty afterward, you must follow up with a high-frequency "polishing" pass from Phase 2 (e.g., 20ns @ 1000kHz) to smooth out the cratered texture.
