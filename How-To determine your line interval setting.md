To find the "perfect" Line Interval, you are essentially looking for the balance between Spot Overlap and Thermal Management. If the interval is too wide, you see scan lines (ridges); if it is too tight, you trap heat, causing the metal to melt, warp, or turn "crusty" instead of clean.
Since you now have your winning Speed, Power, and Frequency from the previous tests, you can use a targeted Interval Sweep to finalize your results.
## The Interval Formula
A good starting point for any pulse width is to aim for a 30% to 50% overlap of the laser's spot. On a 100W MOPA with a standard F-Theta lens, your spot size is likely around 0.05mm.

* Color/Polishing: Needs 90%+ overlap (0.001mm – 0.005mm interval) to stack heat.
* Standard Marking: Needs 50% overlap (0.025mm interval).
* Deep Engraving: Needs 20-30% overlap (0.04mm – 0.06mm interval) to allow debris to escape.

------------------------------
## The "Final Tuning" Test Routine
Run this test for any Pulse Width where you want to "perfect" the surface finish.
Library Baseline Setup:

   1. C00 Settings: Use your Winner Pulse, Power, Speed, and Frequency from the previous 17 tests.
   2. Save to Library: MOPA 100W > Final Tuning > [Pulse] Interval Test.

Material Test Generator Config:

* X-Axis (Line Interval): Set based on the Phase of the pulse:
* Phase 1 (1-6ns): 0.001mm to 0.01mm | Count: 10
   * Phase 2 (20-45ns): 0.01mm to 0.05mm | Count: 10
   * Phase 3/4 (60-500ns): 0.03mm to 0.1mm | Count: 10
* Y-Axis: Keep this as a Static (usually 1 row) or vary Power by ±10% to see how the interval reacts to heat.

------------------------------
## Interpreting Interval Results## 1. The "Too Tight" Sign (Over-Melting)

* Visual: The surface looks "foamy," bubbly, or has a raised, rough texture.
* Cause: The laser is hitting the same spot so many times that the metal stays liquid.
* Fix: Increase your Line Interval (e.g., move from 0.02mm to 0.03mm).

## 2. The "Too Wide" Sign (Scan Lines)

* Visual: You can see individual "tracks" or rows, like a plowed field. The mark may look "thin" or streaky.
* Cause: There isn't enough overlap to create a continuous surface reaction.
* Fix: Decrease your Line Interval (e.g., move from 0.05mm to 0.04mm).

## 3. The "Sweet Spot" (Clean Finish)

* Visual: A smooth, consistent matte or satin finish. In deep engraving, the "floor" of the pocket looks flat and doesn't have deep vertical ridges.

------------------------------
## Phase-Specific Interval Targets

| Phase | Pulse Widths | Target Interval | Focus for Test |
|---|---|---|---|
| 1: Color | 1ns - 6ns | 0.001 - 0.008mm | Finding the specific color band. |
| 2: Black | 20ns - 45ns | 0.01 - 0.025mm | Achieving "Matte Black" vs "Shiny Gray". |
| 3: Engrave | 60ns - 150ns | 0.03 - 0.05mm | Smooth floors with no "plow" marks. |
| 4: Deep/Cut | 200ns - 500ns | 0.05 - 0.1mm | Maximum depth without melting the edges. |

## Next Step: The Cross-Hatch
Once you find the perfect interval, try running the test with a 90-degree Cross-Hatch (2 passes). Often, an interval that looks "streaky" in one direction becomes perfectly smooth when hit from both angles.


