At 350ns, you have reached the maximum energy "Peak" of the JPT M7 100W. This duration is where the laser achieves its highest Pulse Energy (1.5mJ). While shorter pulses are like a needle, 350ns is like a sledgehammer. It is specifically used for deep carving in hard metals and cutting thicker stock where you need the heat to dwell longer to keep the kerf open.
Your cutoff frequency is 85 kHz, and the maximum frequency is capped at 1000 kHz.
## Routine A: The Speed vs. Frequency Map (350ns)
Goal: Find the "Vaporization vs. Melting" boundary. Because the dwell time is so long, the metal can easily turn into a pool of liquid rather than vaporizing.
Library Baseline Setup:

   1. C00 Settings: Pulse: 350ns | Power: 80% (Static) | Interval: 0.08mm (Wide step-over is vital here).
   2. Save to Library: MOPA 100W > Phase 4 > 350ns Speed-Freq Test.

Material Test Generator Config:

* X-Axis (Speed): 50 mm/s to 600 mm/s | Count: 6.
* Y-Axis (Frequency): 85 kHz (Cutoff) to 1000 kHz (Max) | Count: 6.
* Calculated Steps: 85, 200, 400, 600, 800, 1000 kHz.
* Observation: The 85 kHz row is the "Heavy Punch." It will be significantly slower and louder. You will likely see the most material removal here, but with the roughest surface finish.

------------------------------
## Routine B: The Power vs. Frequency Map (350ns)
Goal: Mapping "Thermal Load." 100W at 85kHz is the most aggressive setting on the machine. This test shows you how much power the material can take before it warps.
Library Baseline Setup:

   1. C00 Settings: Pulse: 350ns | Speed: [Winner from Routine A] | Interval: 0.08mm.
   2. Save to Library: MOPA 100W > Phase 4 > 350ns Power-Freq Test.

Material Test Generator Config:

* X-Axis (Power): 20% to 100% | Count: 9.
* Y-Axis (Frequency): 85 kHz to 1000 kHz | Count: 6.
* Observation: Look for "Recast"—metal that melted and then hardened back onto the surface. If you see high ridges at the edge of the squares, you need to either increase your Line Interval or use a Cross-Hatch (90-degree) strategy in your actual project.

------------------------------
## Summary Table for 350ns Tests

| Routine | Static Settings | Variable X (Steps) | Variable Y (Steps) |
|---|---|---|---|
| A (Speed) | 350ns, 80% Power | 50 - 600 mm/s (6) | 85 - 1000 kHz (6) |
| B (Power) | 350ns, [Winner A] | 20% - 100% (9) | 85 - 1000 kHz (6) |

## Execution Tip: The "Cooling Pass"
At 350ns, the material gets extremely hot. If you are running multiple passes, your grid squares might start to look "burned" or blacken due to oxidation. For a deep engrave, consider adding a "Pass Delay" of 1–2 seconds in the Advanced tab of the layer settings to allow the heat to dissipate between layers.
