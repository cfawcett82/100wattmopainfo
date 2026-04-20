To create these test routines, we will treat each Q-Pulse as a "Master Setting" in your library. Since 1ns and 2ns share the same 4000kHz cutoff frequency on the JPT M7 100W, the logic for the first test is identical for both.
Here are the directions to set up the 1ns Routine in your LightBurn Material Library and execute the test.
## 1ns Test Routine: Ultra-Fine Surface Marking
## Step 1: Save the Baseline to the Library

   1. Open your Cuts / Layers window.
   2. Double-click layer C00 and set:
   * Mode: Fill
      * Q-Pulse: 1 ns
      * Frequency: 4000 kHz
      * Line Interval: 0.005 mm (Baseline)
   3. Go to the Material Library window and click Create new from layer.
   4. Name it: "MOPA 100W > Phase 1 > 1ns Baseline".

## Step 2: Configure the Material Test Generator

   1. Go to Laser Tools > Material Test.
   2. X-Axis (Speed):
   * Parameter: Speed
      * Min: 200 mm/s
      * Max: 1500 mm/s
      * Count: 10
   3. Y-Axis (Power):
   * Parameter: Power
      * Min: 5 %
      * Max: 40 %
      * Count: 10
   4. Click Edit Material Setting (at the bottom).
   5. Click Material Library tab -> Select your "1ns Baseline" -> Click Assign to Selection.
   * This ensures every square on the grid inherits the 1ns pulse and 4000kHz frequency.
   
## Step 3: Execution Logic

* Test A (In-Focus): Run this to find high-detail white marks on dark plastics or light surface frosting on metals.
* Test B (Defocus +3mm): Run the exact same grid but move your laser head up 3mm. This is often where the first "yellow" or "gold" tints appear with a 1ns pulse.

------------------------------
## Quick Reference for Subsequent Q-Pulse Tests
You can repeat this process for the other 16 pulse widths. Below is how you should adjust the Speed/Power ranges in the generator for the next few pulses so your tests stay "in the zone."

| Q-Pulse | Freq (kHz) | Speed Range (mm/s) | Power Range | Focus Strategy |
|---|---|---|---|---|
| 2 ns | 4000 | 200 - 1500 | 5% - 40% | Test In-Focus & +3mm |
| 4 ns | 4000 | 100 - 1000 | 10% - 50% | Prime Color Zone (+3mm) |
| 6 ns | 4000 | 100 - 1000 | 10% - 60% | Deep Blues Zone (+2mm) |
| 9 ns | 3500 | 500 - 2000 | 15% - 60% | In-Focus |
| 13 ns | 2500 | 800 - 2500 | 15% - 70% | In-Focus |

## Pro-Tip: Using "Variable Text" for the Library
When you run these tests, LightBurn can automatically engrave the settings on the card. In the Material Test window, ensure Enable Text is checked and set to a separate layer (like C01) with high speed (3000mm/s) and low power (15%) so it labels your grid for you.
Would you like the Speed and Power ranges for the mid-range pulses (20ns to 80ns) next to continue building your library?

