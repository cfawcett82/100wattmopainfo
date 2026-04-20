At 500ns, you have reached the maximum "Dwell Time" of your JPT M7. This setting is less about a sharp punch and more about maximum heat saturation. While 350ns has a slightly higher peak pulse energy, 500ns keeps the laser "on" for the longest possible duration per pulse. This makes it the absolute best setting for cutting thin metal, drilling holes, or clearing deep channels in stubborn materials.
Your cutoff frequency is 67 kHz, and the maximum is 1000 kHz.
## Routine A: The Speed vs. Frequency Map (500ns)
Goal: Find the "Melting Point." Since the dwell is so long, you are looking for the frequency that allows for a "clean cut" vs. a "messy melt."
Library Baseline Setup:

   1. C00 Settings: Pulse: 500ns | Power: 80% (Static) | Interval: 0.1mm (Maximum spacing to prevent the part from glowing cherry red).
   2. Save to Library: MOPA 100W > Phase 4 > 500ns Speed-Freq Test.

Material Test Generator Config:

* X-Axis (Speed): 25 mm/s to 500 mm/s | Count: 10.
* Y-Axis (Frequency): 67 kHz (Cutoff) to 1000 kHz (Max) | Count: 6.
* Calculated Steps: 67, 150, 300, 500, 750, 1000 kHz.
* Observation: The 67 kHz row is for pure destruction. This is where you will see the deepest penetration but the roughest edges.

------------------------------
## Routine B: The Power vs. Frequency Map (500ns)
Goal: Stress test the heat-soak. 100W at 500ns/67kHz is the thermal limit of the machine. This test shows you if the material will survive the pass or just buckle.
Library Baseline Setup:

   1. C00 Settings: Pulse: 500ns | Speed: [Winner from Routine A] | Interval: 0.1mm.
   2. Save to Library: MOPA 100W > Phase 4 > 500ns Power-Freq Test.

Material Test Generator Config:

* X-Axis (Power): 20% to 100% | Count: 9.
* Y-Axis (Frequency): 67 kHz to 1000 kHz | Count: 6.
* Observation: Look for Burr formation. If the edges of the square have a "rim" of metal that you could cut your finger on, you are dumping too much energy. Try a wider Interval or higher Speed.

------------------------------
## Summary Table for 500ns Tests

| Routine | Static Settings | Variable X (Steps) | Variable Y (Steps) |
|---|---|---|---|
| A (Speed) | 500ns, 80% Power | 25 - 500 mm/s (10) | 67 - 1000 kHz (6) |
| B (Power) | 500ns, [Winner A] | 20% - 100% (9) | 67 - 1000 kHz (6) |

## Final Project Wrap-Up
You have now mapped all 17 pulse widths. To finalize your Material Library:

   1. Compare your 1ns and 500ns cards: Notice how 1ns is purely "optical" (light/color) while 500ns is purely "mechanical" (depth/removal).
   2. The 3D Recipe: Most professionals use 200ns-350ns for the "digging" passes and then finish with a 2ns-6ns pass at high frequency to "clean" the soot and polish the floor.
