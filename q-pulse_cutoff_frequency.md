# JPT MOPA M7 100W Q-Pulse Cutoff Frequency Guide

For the JPT MOPA M7 100W (specifically the **YDFLP-E2-100-M7-M-R**), it is critical to use the correct **Cutoff Frequency** for each pulse width to ensure you are actually outputting the full **100W** of power.

Using a frequency below the cutoff will result in a linear drop in average power, while going above the cutoff will keep the power stable but reduce the energy per individual pulse.

## JPT M7 100W Pulse Width & Cutoff Frequency Table

| Pulse Width (ns) | Cutoff Frequency (kHz) | Max Bandwidth (kHz) | Primary Application Notes |
|---|---:|---:|---|
| 2 ns | ~4000 kHz | 4000 kHz | Ultra-delicate surface marking, high-contrast colors. |
| 4 ns | ~4000 kHz | 4000 kHz | Bright colors on stainless steel. |
| 6 ns | ~4000 kHz | 4000 kHz | Fine detail, subtle surface frosting. |
| 9 ns | ~3500 kHz | 4000 kHz | Precision marking on plastics. |
| 13 ns | ~2500 kHz | 4000 kHz | Dark marks on delicate plastics. |
| 20 ns | ~1500 kHz | 4000 kHz | Anodized aluminum marking. |
| 30 ns | ~1000 kHz | 4000 kHz | General-purpose high-speed marking. |
| 45 ns | ~660 kHz | 4000 kHz | Balancing heat and material removal. |
| 60 ns | ~500 kHz | 4000 kHz | Standard engraving on most metals. |
| 80 ns | ~375 kHz | 4000 kHz | Deeper engraving with controlled heat. |
| 100 ns | ~300 kHz | 4000 kHz | Rapid material ablation. |
| 150 ns | ~200 kHz | 4000 kHz | Deep metal engraving. |
| 200 ns | ~150 kHz | 2000 kHz | Maximum punch for hard metals. |
| 250 ns | ~120 kHz | 1000 kHz | Aggressive material removal. |
| 350 ns | ~85 kHz | 1000 kHz | Reaches max pulse energy (1.5 mJ). |
| 500 ns | ~67 kHz | 1000 kHz | Max "punch" for deep carving/cutting. |

> **Note:** JPT sources often skip certain values digitally. While you can input 1 ns, the laser source may default to 2 ns as its minimum physical capability.

## Testing Strategy Recommendation

1. **Constant Power/Speed**: Keep your power at 100% and speed constant across your test squares.
2. **Match Frequency to Q-Pulse**: For the most accurate "power capability" test, set each square to its specific cutoff frequency from the table above.
3. This ensures you are testing what 100W looks like at every single pulse flavor.

## Reference

- LightBurn Software Forum discussions on JPT MOPA cutoff behavior and pulse-width/frequency tuning.